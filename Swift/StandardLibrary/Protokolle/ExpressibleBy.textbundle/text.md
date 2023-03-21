# ExpressibleBy
🦎

## Beispiel: Array
Damit kann man sagen, dass sich ein Typ aus einem anderen Typ erstellen lassen können soll.

Beispiel mit einer eigenen Stack-Klasse

```swift
extension Stack: ExpressibleByArrayLiteral {
    init(arrayLiteral elements: Element...) {
        self.array = elements
    }
}
```

Jetzt kann man den Stack so verwenden:

```swift
var numbers: Stack = [1, 2, 3, 4, 5]
```

Es gibt auch andere Varianten, zum Beispiel `AccessibleByStringLiteral`

## Beispiel String


```swift
extension URL: ExpressibleByStringLiteral {
    public init(stringLiteral value: String) {
        self = URL(string: value)!
    }
}
```

Jetzt kann man es direkt so erstellen:

```swift
let url: URL = "https://www.hackingwithswift.com"
```

## Zusammenfassung
- Wie lässt sich ein eigener Typ aus einem Array, String etc. erstellen?


#learning unit#