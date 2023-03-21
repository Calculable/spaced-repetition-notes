# CompactMap
🗜️

## Anwendungsfall: Eine Mapping-Funktion, die Optionals produziert

```swift
let recreatedNumbers = stringNumbers.map(Int.init)
print(recreatedNumbers) //That will output `[Optional(4), Optional(8), Optional(15), Optional(16), Optional(23)]`
```

## Lösung: Compact Map

- Hier werden alle Werte ausgepackt. Wenn ein Wert nil ist, wird er einfach übersprungen:

```swift
let recreatedNumbers = stringNumbers.compactMap(Int.init)
print(recreatedNumbers) //That will output `[4, 8, 15, 16, 23]`
```


## Weiterer Anwendungsfall 1

Wenn man eine Collection hat, welche verschiedene Typen enthält und wir alle Instanzen eines bestimmten Typen auslesen möchten:

```swift
let enemies = spriteKitSkNode.children.compactMap { $0 as? EnemyNode }
```

## Weiterer Anwendungsfall 2

Häufig wird `compactMap` auch so aufgerufen, wenn man einfach nur die `nil`-Werte entfernen möchte:

```swift
xy.compactMap { $0 }
```

## Zusammenfassung
- Wie funktioniert CompactMap?



#learning unit#