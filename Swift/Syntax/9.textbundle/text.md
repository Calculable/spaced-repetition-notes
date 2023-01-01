# Initializer 🛫
::9::

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

## Super Initializer aufrufen
Wenn man kein `override` schreibt, wird der Super-Initializier Implizit aufgerufen:
```swift
init(color: String) {
	self.color = color
	// super.init() implicitly called here
}
```

Wenn man `override` schreibt, wird der Super-Initializier explizit aufgerufen:

```swift
 override init() {
	super.init()
	numberOfWheels = 2
}
```


##  Failable Initializers

Beachte: Es wird hier nicht einfach ein Fehler geworfen!

```swift
struct Animal {
    let species: String
    init?(species: String) {
        if species.isEmpty { return nil }
        self.species = species
    }
}
```

> You can delegate from init? to init! and vice versa, and you can override init? with init! and vice versa. You can also delegate from init to init!, although doing so will trigger an assertion if the init! initializer causes initialization to fail.

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
Override
Failable
Required
Wann wird der super-init aufgerufen?