# .formatted()
🖨️
- Für verschiedene Typen
- Beispiele:

```swift
["a", "b", "c", "d"].formatted(.list(type: .or))
```

```swift
Date.now.formatted(.dateTime.hour().minute())
```

```swift
0.10.formatted(.percent.precision(.fractionLength(1)))
```

```swift
let weight = Measurement(value: 20, unit: UnitLength.centimeters)
return weight.formatted()
```


## Zusammenfassung

- Mit welcher Funktion kann man verschiedene Typen formatiert ausgeben? (nicht den genauen Code auswändig)

#learning unit#