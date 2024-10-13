# Swift 6: Data Races eliminieren

##  Konfiguration

### Xcode: pro Target

- Hinweis: In der Xcode 16 Beta hat man bessere Fehlermeldungen / Vorschläge
- Der neue Modus ist Opt-In

**Um bei Data Races eine Warnung anzuzeigen:**

![][image-1]

**Um bei Data Races einen Fehler anzuzeigen:**

![][image-2]

### Alternativ: Package Manifest

> A Package.swift file that uses swift-tools-version of 6.0 will enable the Swift 6 language mode for all targets.  However, you can now also change the language mode as needed on a per-target basis using the new swiftLanguageVersion build setting:

```swift
// swift-tools-version: 6.0


let package = Package(
    name: "MyPackage",
    products: [
        // ...
    ],
    targets: [
        // Uses the default tools language mode
        .target(
            name: "FullyMigrated",
        ),
        // Still requires 5
        .target(
            name: "NotQuiteReadyYet",
            swiftSettings: [
                .swiftLanguageVersion(.v5)
            ]
        )
    ]
)
```

### Tipps: Migration

- Modul für Modul einzeln migrieren
- Mit dem äussersten Modul starten


## Szenario: Globale oder statische Variablen

### Beispiel: Error in Swift 6

> var 'myGlobalVariable' is not concurrency-safe because it is non-isolated global shared mutable state; this is an error in the Swift 6 language mode

```swift
var myGlobalVariable = ...
```

### Lösung: Sendable let

- Wenn der Typ der Variable `Sendable` ist und die Variable nur lesend verwendet wird, kann man sie zu einem `let` machen:

```swift
let myGlobalVariable = ...
```

### Lösung: @MainActor
- Falls man jedoch zwingend `var` braucht, muss man einen Synchronisationsmechanismus implementieren, z.B

```swift
@MainActor var myGlobalVariable = ...
```

### Lösung: eigener Synchronisationsmechanismus
- Wenn man einen eigenen Synchronisationsmechanismus hat:

```swift
/// There is a custom lock to protect access to this variable
nonisolated(unsafe) var myGlobalVariable = 42
```

## Szenario: Delegate Methode

### Beispiel: Error in Swift 6

Man hat eine @MainActor Klasse, verwendet jedoch eine Delegate-Methode, welches nicht garantiert auf dem MainActor läuft:

> warning: Main actor-isolated instance method 'doSomething()' cannot be used to satisfy nonisolated protocol requirement

```swift
@MainActor
class MyClass {
}

extension MyClass: MyDelegate {
    func doSomething() {
        //...
    }
}
```

### Lösung: nonIsolated

- Wenn die Delegate-Methode nicht zwingend auf dem MainActor laufen muss:

```swift
nonisolated func doSomething() 
		
}
```


### Lösung: @MainActor

- wenn man das Delegate verändern kann:

```swift
@MainActor
protocol MyDelegate: AnyObject {
    //...
}
```

### Lösung: Package aktualisieren
- wenn man das Delegate selbst nicht verändern kann
- Allenfalls gibt es für das Package mit dem Delegate bereits eine Swift-6 kompatible Version

### Lösung: MainActor.assumeIsolated / @preconcurrency
- Wenn man das Delegate nicht unter Kontrolle hat, aber weiss, dass es auf immer auf dem MainActor aufgerufen wird (weil das z.B. in der Dokumentation erwähnt wird):

![][image-3]

```swift
extension MyClass: MyDelegate
    nonisolated func doSomething() {
        MainActor.assumeIsolated {
            //...
        }
    }
}
```

- Dafür gibt es auch eine Shorthand-Syntax:

```swift
extension MyClass: @preconcurrency MyDelegate {
    func doSomething() {
        //...
    }
}
```

###  Lösung: Neuer Task

- Wenn man das Delegate nicht unter Kontrolle hat und auch nicht weiss, auf welcher Queue es läuft:

```swift
nonisolated func doSomething() {
    Task { @MainActor in
		//....      
    }
}
```

## Szenario: Eine @MainActor-isolierte Instanz verwenden

### Beispiel: Error in Swift 6

> //warning: Call to main actor-isolated class method 'shared()' in a synchronous nonisolated context

```swift
func example() {
    let watchExtension = WKApplication.shared()
}
```

### Lösung in einem synchronen Kontext: @MainActor

```swift
@MainActor func example() {
    let watchExtension = WKApplication.shared()
}
```

oder:

```swift
func example() {
	Task { @MainActor
    	let watchExtension = WKApplication.shared()
	}
}
```

### Lösung in einem asynchronen Kontext: await

Man muss "awaiten" bis die Main Queue verfügbar wird:

```swift
func example() async {
    let watchExtension = await WKApplication.shared()
}
```

##  Szenario: Shared mutable state zwischen zwei actors

###  Beispiel: Error in Swift 6
> warning: Sending 'self.myVariable' risks causing data races

```swift
@MainActor class MyClass {
	//...
	await anotherActor.doSomething(self.myVariable)
	///...
}
```

###  Lösung: Typ "Sendable" machen

- Wenn man den Typ von `myVariable` unter Kontrolle hat.

### Lösung: Preconcurrency

- Wenn man den Typ von `myVariable` nicht unter Kontrolle hat (externe Library), aber man weiss dass die Variable eigentlich Sendable ist:

> you can use a @preconcurrency import to downgrade diagnostics until the library is updated, the error will be downgraded to a warning

```swift
@preconcurrency import MyVariableLibrary


@MainActor class MyClass 
	//...
	await anotherActor.doSomething(self.myVariable)
	///...
}
```

### Lösung: @unchecked Sendable

- Wenn man den Typ von `myVariable` nicht unter Kontrolle hat (externe Library), aber man weiss dass die Variable eigentlich Sendable ist:

```swift
extension MyVariableType: @retroactive @unchecked Sendable {
}
```

### Lösung: "sending"

- Der Typ bleibt "non-sensable" aber der Empfänger kann garantieren, dass er die Variable nur auf eine "sichere" Weise verwendet:

```swift
//anotherActor

func doSomething(_ myVariable: sending MyVariable) async {
    myVariables.append(myVariable)
}
```

### Lösung: nonisolated

- Wenn man einen eigenen Synchronisierungsmechanismus hat, von dem der Compiler nichts weiss, kann man die Warnungen/Fehler unterdrücken:

```swift
nonisolated(unsafe) var myVariable = ...
```

## Szenario: Im deinit auf actor-isolierte Properties zugreifen

###  Beispiel: Error in Swift 6

deinit läuft nicht auf dem MainActor!

```swift
@MainActor class MyClass {
	deinit {
		//not on the main actor anymore!
		anotherActor.doSomething()
	}
}
```

### Lösung: Task

> Often, the work being done within the deinit does not need to be synchronous. A solution is to use an unstructured Task to first capture and then operate on the isolated values. When using this technique, it is critical to ensure you do not capture self, even implicitly. Never extend the life-time of self from within deinit. Doing so will crash at runtime!


```swift
@MainActor class MyClass 
	deinit {
        Task { [anotherActor] in
            await anotherActor.doSomething()
        }
	}
}
```


###  Lösung: Workaround

Siehe Post von Nici [https://teams.microsoft.com/l/message/19:8e1287403d8944b59a642ca61c4e12c9@thread.skype/1712993701764?tenantId=2fd47b26-4725-4433-be51-4919e4481e38&groupId=fd5bc551-4744-4870-bfdc-2c6831351e71&parentMessageId=1712993701764&teamName=iOS&channelName=I%20learned%20today&createdTime=1712993701764][1]

Siehe [https://medium.com/jamf-engineering/swift-6-upgrade-preparation-0941fbea2db6][2]

```swift
@MainActor class MyClass {
	deinit {
		assumeIsolatedDuringDeinit { actor in
			actor.anotherActor.doSomething()
		}
	}
}



extension MyClass {
    // An actor's deinit is nonisolated so we need to cleanup state that needs to exist past this instance's deinit. Currently there is no way to accomplish this that wouldn't be an error in Swift 6, hopefully that changes at some point. This evolution proposal attempts to address this problem: https://github.com/apple/swift-evolution/blob/main/proposals/0371-isolated-synchronous-deinit.md
    // Method influenced from https://github.com/apple/swift/blob/47803aad3b0d326e5231ad0d7936d40264f56edd/stdlib/public/Concurrency/ExecutorAssertions.swift#L351
    @_unavailableFromAsync(message: "express the closure as an explicit function declared on the specified 'actor' instead")
    private nonisolated func assumeIsolatedDuringDeinit<T>(_ operation: (isolated MyClass) throws -> T) rethrows -> T {
        typealias YesActor = (isolated MyClass) throws -> T
        typealias NoActor = (MyClass) throws -> T

        // To do the unsafe cast, we have to pretend it's @escaping.
        return try withoutActuallyEscaping(operation) { (_ fn: @escaping YesActor) throws -> T in
            let rawFn = unsafeBitCast(fn, to: NoActor.self)
            return try rawFn(self)
        }
    }
}
```


## Übersicht: Common Compiler Errors

[https://www.swift.org/migration/documentation/swift-6-concurrency-migration-guide/commonproblems/][3]

##  Good to know

- Globale (-\> lazy) Variabeln werden garantiert atomic erstellt (auch wenn zwei Thread "gleichzeitig" darauf zugreifen, was dann aber nur einmalig eine Inisialisierung auslöst)
- Neu sind alle SwiftUI Views an den MainActor gebunden
- Swift does not intfer sendability for public types automatically because because marking a type sendable is a guarantee to the clients - deshalb muss man es explizit machen.

[1]:	https://teams.microsoft.com/l/message/19:8e1287403d8944b59a642ca61c4e12c9@thread.skype/1712993701764?tenantId=2fd47b26-4725-4433-be51-4919e4481e38&groupId=fd5bc551-4744-4870-bfdc-2c6831351e71&parentMessageId=1712993701764&teamName=iOS&channelName=I%20learned%20today&createdTime=1712993701764
[2]:	https://medium.com/jamf-engineering/swift-6-upgrade-preparation-0941fbea2db6
[3]:	https://www.swift.org/migration/documentation/swift-6-concurrency-migration-guide/commonproblems/

[image-1]:	assets/Bildschirmfoto%202024-06-18%20um%2019.04.01.png
[image-2]:	assets/Bildschirmfoto%202024-06-18%20um%2019.10.35.png
[image-3]:	assets/DraggedImage.png

#guide