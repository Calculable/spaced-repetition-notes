# Box Type
🎁

## Um was geht es?

- Einen Struct in einer Klasse verpacken, um die Instanz an verschiedenen Orten zu teilen.

> To be clear, boxing is an _exception_ and not the _rule_: when you see boxing happening it’s a strong statement that the developer who used it specifically wants one piece of data to be shared, but normally not shared.


## Code

```swift
final class Box<Type> {
    var value: Type

    init(_ value: Type) {
        self.value = value
    }
}
```

## Erweiterung

Wenn man mit dem Box-Typ arbeitet verliert man viele praktische Funktionen (zum Beispiel kann man den gewrappten Typ nicht mehr so einfach direkt auf der Konsole ausgeben).

Dank Extensions kann man diese Funktionalität jedoch wieder zurückbekommen:


```swift
extension Box: CustomStringConvertible where Type: CustomStringConvertible {
    var description: String {
        value.description
    }
}
```

```swift
extension Box: Equatable where Type: Equatable {
    static func ==(lhs: Box, rhs: Box) -> Bool {
        lhs.value == rhs.value
    }
}

extension Box: Comparable where Type: Comparable {
    static func <(lhs: Box, rhs: Box) -> Bool {
        lhs.value < rhs.value
    }
}
```

```swift
extension Box: Hashable where Type: Hashable {
    func hash(into hasher: inout Hasher) {
        hasher.combine(value)
    }
}
```

```swift
extension Box: Identifiable where Type: Identifiable {
    var id: Type.ID { value.id }
}
```

## Zusammenfassung

- Wozu ist Boxing gut?
- Wie sieht ein einfacher Box-Typ aus? (Code)


#nur learning unit#