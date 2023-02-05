# Computed Properties ℹ️

## Computed Properties / Setter- und Getter

```swift
 var perimeter: Double {
        get {
            return 3.0 * sideLength //alternativ: ohne return
        }
        set { //alternativ set(myNewVariableName)
            sideLength = newValue / 3.0 //beachte: newValue
        }
 }
```
(Kann auch nur Read- oder Write-Only sein)

## Zusammenfassung
Codebeispiel