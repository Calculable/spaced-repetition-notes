# Initializer 🛫

## Designated Initializer
- Initializiert alle Properties
- Beachte: Man kann mehrere haben:

```swift
init(fromFahrenheit fahrenheit: Double) {
	temperatureInCelsius = (fahrenheit - 32.0) / 1.8
}
```

##  Convenience Initializier

Definition: Rufen einen Designated Initializer mit Default-Werten auf

```swift
convenience init(parameters) {
    statements
	self.init(...)
}
```

##  Required Initializers

- Müssen von jeder Subklasse implementiert werden

```swift
class SomeClass {
    required init() {
        // initializer implementation goes here
    }
}
```

`required` wird dann auch bei der Implementation in der Subklasse geschrieben, dafür braucht man das `override` nicht mehr

## Zusammenfassung
Designated
Convenience
Required
