# Der Typ StaticString
💬
## Was ist ein Static String?
- StaticStrings sind immer Hardcodierte Strings
- StaticStrings können also nicht dynamisch erzeugt werden oder mittels String Interpolation

## Anwendungsfälle

### Beispiel 1: URL
- So kann man StaticStrings zum Beispiel nutzen, um eine Extension für URL zu bauen, die jeweils beim Initializer eine URL zurückgibt statt eine Optional URL, wenn ein Hardcodierter String verwendet wird:

```swift
extension URL {
    init(_ string: StaticString) {
        if let url = URL(string: "\(string)") { //beachte: Man kann den String nicht direkt übergeben
            self = url
        } else {
            fatalError("Illegal URL: \(string)")
        }
    }
}
```

### Beispiel 2: Regular Expressions
Oder auch bei Regular Expressions könnte man das gleiche Prinzip anwenden:

```swift
extension NSRegularExpression {
    convenience init(_ pattern: StaticString) {
        do {
            try self.init(pattern: "\(pattern)")
        } catch {
            preconditionFailure("Illegal regex: \(pattern).")
        }
    }
}
```

## Zusammenfassung
- Was sind Static Strings?
- Wozu sind sie praktisch (Anwendungsfälle)



#nur learning unit#