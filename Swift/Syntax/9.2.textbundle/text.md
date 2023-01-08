# Failable Initializer 🛫
::9.2::

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


## Zusammenfassung
Wie funktioniert ein Failable Initializer?





