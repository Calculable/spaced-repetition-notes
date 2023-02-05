# Textfeld für numerische Werte 🧩

```swift
TextField("Amount", value: $checkAmount, format: .currency(code: Locale.current.currencyCode ?? "USD"))
    .keyboardType(.decimalPad)
```

## Zusammenfassung
Wie macht man ein Textfeld? (numerisch)