# Methodenreferenzen als Closure (Theorie)
🔄

## Fazit
- Methoden-Referenzen habe eine strong reference zu self

##  Beispiel mit Klasse

Hier hat man einen Retain Cycle:

```swift
class A {
    var b: B? = nil

    func connect() {
        b = B(callback: self.doSomething)
    }

    func doSomething() {
        print("Something")
    }
}

class B {
    let callback: () -> ()

    init(callback: @escaping () -> Void) {
        self.callback = callback
    }
}
```


![][image-1]

Mögliche Lösung:

- b könnte nicht als weak gekennzeichnet werden, weil ansonsten die Referenz zu b direkt verloren geht
- das callback könnte nicht als weak gekennzeichnet werden, weil das nur für Klassentypen möglich ist

```swift
class A {
    var b: B? = nil

    func connect() {
        b = B(callback: { [weak self] in
            self?.doSomething()
        })
    }

    func doSomething() {
        print("Something")
    }
}

class B {
    let callback: () -> ()

    init(callback: @escaping () -> Void) {
        self.callback = callback
        callback()
    }
}
```

![][image-2]

Weitere Lösung: Man macht die Funktion statisch:

```swift
class A {
    var b: B? = nil

    func connect() {
        b = B(callback: Self.doSomething)
    }

    static func doSomething() {
        print("Something")
    }
}

class B {
    let callback: () -> ()

    init(callback: @escaping () -> Void) {
        self.callback = callback
        callback()
    }
}
```

##  Beispiel mit Struct

Hier hat man keinen Retain-Cycle weil man als Callback eine Kopie übergibt:

```swift
struct A {
    var b: B? = nil

    mutating func connect() {
        b = B(callback: self.doSomething)
    }

    func doSomething() {
        print("Something")
    }
}

class B {
    let callback: () -> ()

    init(callback: @escaping () -> Void) {
        self.callback = callback
        callback()
    }
}
```


![][image-3]

##  Praxisbeispiel

Siehe: [ulysses://x-callback-url/open?id=M0eZ\_X2T1uMA6-Iy2cmchg][1]

##  Zusammenfassung
- Siehe zwei Codebeispiele: Was geschieht in diesem Fall?

[1]:	ulysses://x-callback-url/open?id=M0eZ_X2T1uMA6-Iy2cmchg

[image-1]:	assets/DraggedImage.png
[image-2]:	assets/DraggedImage-1.png
[image-3]:	assets/DraggedImage-2.png

#learning unit# #guide