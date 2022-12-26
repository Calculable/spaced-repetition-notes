#  Protocol Associated Type
::18::

## Für was sind Protocol Associated Types?

Oft braucht man associated types, weil Protokolle keine generischen Parameter erlauben:

```swift
protocol Product<T> {} //fehler: protocols do not allow generic parameters; use associated types instead
```

stattdessen schreibt man:

```swift
protocol Product {
	associatedtype Code
	var productCode: Code {get}
}

struct Laptop : Product {
	typealias Code = Int
	var productCode = 6 
}
```

## Problem: Protokoll mit Associated Type kann nicht selbst als Typ verwendet werden

Jetzt hat man jedoch ein Problem. Folgende Dinge sind jetzt nicht mehr möglich:

```swift
let cache: [MyProtocol] //Fehler
struct MyItem {
    let item: MyProtocol //Fehler
    let expiryDate: Date
    ...
}
```

Die Lösung für dieses Problem ist Type Erasure