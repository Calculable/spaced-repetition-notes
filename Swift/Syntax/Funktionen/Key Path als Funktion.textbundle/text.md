# Key Path als Funktion
📌
## Wie wird es angewendet?

> write a key path such as `\X.y` then you can use that in place of functions that expect an `X` and return `y`.

- Seit Swift 5.2

## Beispiel

```swift
let nameCounts2 = names.map(\.count)
print(nameCounts2)
```

Beachte: Es braucht keine geschweiften Klammern hier

## Zusammenfassung
- Wie können Key Paths als Funktion verwendet werden?


#learning unit#