# Override beim Konstruktor
🧠
- Konstruktoren standartmässig nicht vererbt. Ausser wenn man selbst keinen „Designated“ initializer anbietet, werden alle Designated Initializers vererbt.
- Es stimmt nicht, dass man beim Konstruktor das „Override“ Schlüsselwort generell weglassen darf

![][image-1]

- Wenn der Konstruktor die gleiche Signatur hat, wie der Konstruktor der Oberklasse, dann muss man das `override`-Schlüsselwort angeben
- ABER: Wenn der Parent einen Konstruktor ohne Argumente hat, dann muss man nicht explizit `super.init()` aufrufen:

```swift
class Vehicle {
    var speed: Double
    
    init() {
        self.speed = 50
    }
}

class Car: Vehicle {
    var color: String
    
    init(color: String) {
        self.color = color
    }
}

var car = Car(color: "Red")

```

## Zusammenfassung
- Darf man das `override`-Keyword beim Konstruktor weglassen?
- Wann muss man `super.init()` explizit aufrufen und wann wird es automatisch aufgerufen?

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-02-13%20um%2016.33.50.png