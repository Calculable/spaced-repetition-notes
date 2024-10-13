# Property Wrapper
📦

## Wie funktionieren Property Wrapper?
- Hinter jedem Property Wrapper ist ein Struct
- Zum Beispiel steht hinter `@State` und `@Environment` immer ein Struct. (`State<Value>`)

## Beispiel

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


## Verwendung mit Variabel
```swift
struct User {
    @NonNegative var score = 0
}
```


## Verwendung mit Parameter

Neu in Swift 5.5

- Der Wert wird transformiert, bevor man ihn in der Funktion verwendet


```swift
func setScore2(@Clamped(range: 0...100) to score: Int) {
    print("Setting score to \(score)")
}

setScore2(to: 50)
setScore2(to: -50)
setScore2(to: 500)
```


## Zusammenfassung
Zweck
Custom Property Wrapper (nur Konzept)

#learning unit# #guide