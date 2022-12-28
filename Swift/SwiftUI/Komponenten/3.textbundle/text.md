# Textfeld
::3::

##  Beispiel
```swift
TextField("Amount", value: $checkAmount, format: .currency(code: Locale.current.currencyCode ?? "USD"))
    .keyboardType(.decimalPad)
```

