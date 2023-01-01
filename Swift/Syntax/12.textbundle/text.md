# Property Wrapper 📦
::12::

## Wie funktionieren Property Wrapper?
- Hinter jedem Property Wrapper ist ein Struct
- Zum Beispiel steht hinter `@State` und `@Environment` immer ein Struct. (`State<Value>`)


##  Custom Property Wrapper (nicht auswändig)

### Custom Property Wrapper Definition
```swift
@propertyWrapper
struct NonNegative<Value: BinaryInteger> {
    var value: Value

    init(wrappedValue: Value) {
        if wrappedValue < 0 {
            value = 0
        } else {
            value = wrappedValue
        }
    }

    var wrappedValue: Value {
        get { value }
        set {
            if newValue < 0 {
                value = 0
            } else {
                value = newValue
            }
        }
    }
}
```

### Custom Property Wrapper Verwendung
```swift
struct User {
    @NonNegative var score = 0
}
```

## Zusammenfassung
Zweck
Custom Property Wrapper (nur Konzept)