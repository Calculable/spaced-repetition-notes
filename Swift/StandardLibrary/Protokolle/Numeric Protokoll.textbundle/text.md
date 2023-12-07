# Numeric Protokoll
💯
- Wird implementiert von `Int`, `Double` etc.

```swift
func count<Number: Numeric>(numbers: [Number]) {
    let total = numbers.reduce(0, +)
    print("Total is \(total)")
}
```

übrigens könnte man diesen Code auch so schreinen:

```swift
func count(numbers: [some Numeric]) {
    let total = numbers.reduce(0, +)
    print("Total is \(total)")
}
```

## Zusammenfassung
- Wozu ist das Protokoll Numeric gut?


#learning unit#