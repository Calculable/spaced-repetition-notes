# Textfeld 🧩
::3::

##  Beispiel für Zahlen
```swift
TextField("Amount", value: $checkAmount, format: .currency(code: Locale.current.currencyCode ?? "USD"))
    .keyboardType(.decimalPad)
```

## Beispiel für Text

```swift
TextField("Github Username", text: $username)
```

## Zusammenfassung
Wie macht man ein Textfeld? (numerisch oder mit Text)