# Lazy Sequence 🦥

## Zweck
Die Zahlen werden erst berechnet, wenn sie benötigt werden

##  Beispiel
Hier würden alle Zahlen sofort berechnet:

```swift
let doubled = numbers.map { $0 * 2 }
```

Wenn man das nicht möchte, schreibt man:

```swift
let lazyDoubled = numbers.lazy.map { $0 * 2 }
```

##  Zusammenfassung
- Wie wird Lazy Sequence angewendet?