# Default Initializer
🛫

##  Bei Klassen

Wenn man keinen Initializer schreibt und alle Paramter einen Default-Wert haben wird automatisch ein Default Initializer ohne Parameter erzeugt.

##  Bei Structs (Memberwise Initializer)

> Structure types automatically receive a memberwise initializer if they don’t define any of their own custom initializers.

```swift
struct Size {
    var width = 0.0, height = 0.0
}
let twoByTwo = Size(width: 2.0, height: 2.0)
```

> When you call a memberwise initializer, you can omit values for any properties that have default values

```swift
let zeroByTwo = Size(height: 2.0)
```


## Zusammenfassung
- Was ist der Default Initializer bei Structs und Klassen?

#learning unit#