# Begriff: Specialization
⚙️

So wird der Prozess genannt, wenn Swift aus generischen Funktionen zur Compile-Zeit die verschiedenen Varianten mit expliziten Typen erstellt.

Hier würde der Compiler zum Beispiel eine Variante für `Int` und eine Variante für `Double` erzeugen:


```swift
func count<Number: Numeric>(numbers: [Number]) {
    let total = numbers.reduce(0, +)
    print("Total is \(total)")
}
```

```swift
count([1, 2, 3])
```

```swift
count([1.5, 2.5, 3.5])
```

Wenn man statt Generics mit Existantial Types arbeitet ist das nicht möglich (dynamic dispatch statt static dispatch) - deshalb sind existantial types zur Laufzeit weniger schnell als Generics.

## Zusammenfassung
- Was bedeutet der Begriff?



#nur learning unit# #learning unit#