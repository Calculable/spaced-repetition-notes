# Tipp: Default Initializer behalten
🛫

Wenn man im Struct einen eigenen Initializer schreibt, dann wird der default Initializer in der Regel gelöscht.

Dieses Problem kann man so Verhindern, indem man den Initializer in einer Extension hinzufügt:

```swift
struct Person {
    var firstName: String
    var lastName: String
}

extension Person {
    init(name: String) {
        let split = name.components(separatedBy: " ")
        firstName = split.first ?? ""
        lastName = split.last ?? ""
    }
}
```

##  Zusammenfassung
- Wie kann man den Default-Initializer behalten, wenn man in einem Struct einen eigenen Initializer hinzufügt?

#learning unit#