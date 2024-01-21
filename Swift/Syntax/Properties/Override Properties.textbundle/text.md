# Override Properties
🖋️

- Das Property der Subklasse muss natürlich ein Computed Property sein, sonst macht es keinen Sinn es zu überschreiben

```swift
class BaseClass {
    var storedProperty: Int = 0
}

class SubClass: BaseClass {
    override var storedProperty: Int {
        get {
            // Return some computed value here.
            return super.storedProperty * 2
        }
        set {
            // Optionally, you can also intercept the setting of the property.
            super.storedProperty = newValue / 2
        }
    }
}
```

## Zusammenfassung
- Wie überschreibt man eine Property aus der Oberklasse?


#learning unit#