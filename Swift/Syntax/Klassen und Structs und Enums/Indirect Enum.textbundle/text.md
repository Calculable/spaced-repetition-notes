# Indirect Enum
🚏

Genau so wie ein Struct nicht auf sich selbst referenzieren kann (weil es sonst unendlich gross wird), kann auch ein Enum nicht auf sich selbst referenzieren.

Man kann aber das `indirect` keyword verwenden. Das bedeutet, dass Swift intern das verlinkte Enum als Referenz ablegt

So wird es möglich, verschachtelte Enums zu erstellen

```swift
indirect enum MyEnum {
    case xy(value: MyEnum?)
}
```

## Zusammenfassung
- Was ist ein Indirect Enum (nur Theorie)


#nur learning unit# #learning unit#