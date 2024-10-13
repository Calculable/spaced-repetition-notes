# Sendable
🔒

## Sendable Protokoll

###  Zweck
- Das Protokoll drückt aus, dass ein Typ Thread-Safe ist (zum Beispiel durch interne Locks)

> A Sendable type is one that can be safely passed around in a concurrent environment

> he Sendable attribute is used to annotate types that are known to be safe to pass between tasks. By designating a type as Sendable, Swift ensures that it is safe to share and access that type across multiple concurrent tasks without causing data corruption or synchronization issues. 

###  Was ist automatisch konform zu Sendable?
- Basisdatentypen (`Int`, `String`, `Bool`, …)
- Optionals
- Standart Library Collections mit den Basis-Datentypen:  `Array<String>` or `Dictionary<Int, String>`
- Tuples
- Actors (!) - Häufig die einfachste Lösung wenn ein Typ Sendable sein muss
- Structs oder Enums, welche nur `Sendable` properties enthalten

```swift
// Implicitly conforms to Sendable
struct MyCustomStruct {
    var mySendableProperty: Int
}
```

=\> Achtung: Es wird nicht aufomatisch konform wenn es sich um einen "public" typen handelt. Hier muss man es explizit sendable machen, da dies ein Teil des "Contracts" ist. Implizites Sendable gilt jeweils nur im eigenen Package.

### Explicit Conformance
- Wenn man selbst weiss, das der Typ Thread-Safe ist, macht man den Typen selbst konform zu `Sendable`
- Eine Klasse muss dazu
	- Von NSObject oder von nichts erben
	- Ale Properties müssen konstant oder konform zu Sendable sein
	- Die Klasse muss `final` sein

```swift
/// User is immutable and therefore thread-safe, so can conform to Sendable
final class User: Sendable {
    let name: String
    init(name: String) { self.name = name }
}
```

Wenn man die Anforderung nicht erfüllt aber trotzdem weiss, dass es Thread-Safe ist, verwendet man `@unchecked Sendable`

```swift
final class MutableUser: @unchecked Sendable {/*...*/}
```


## Verwendung @Sendable

Ein Closure erwarten, nur Thread-Safe Parameter hat

```swift
func filteredArticles(_ isIncluded: @Sendable (Article) -> Bool) async -> [Article] {
        // ...
}
```

Das heisst, man darf beim Aufruf nur Thread-Safe variablen verwenden:
```swift
let filteredArticles = await listOfArticles.filteredArticles { article in
	//hier dürfen jetzt nur Thread-Safe Werte capturen 
}
```

Häufiger Anwendungsfall ist das Closure, das man in einen Task gibt, dieses muss `@Sendable` sein:

```swift
Task { /*Inhalt*/ }  //funktioniert also nur wenn der Inhalt @Sendable ist
```

##  Build Setting

![][image-1]

> This build setting controls the compiler enforcement level of Sendable and actor-isolation checking.

=\> Mit Swift 6 wird "Complete" verpflichtend

## Zusammenfassung
- Wozu wird `Sendable` und `@Sendable` verwendet (nur Konzept)

[image-1]:	assets/Bildschirmfoto%202023-08-02%20um%2008.17.26.png

#learning unit# #guide