# Observed Properties
ℹ️

## Observed Properties: willSet und didSet

```swift
var triangle: EquilateralTriangle {
        willSet { //beachte: newValue
            square.sideLength = newValue.sideLength
        }
		didSet { //hier wird old-value verwendet
			
		}
}
```


=\> Achtung wird nicht bei der Initialisierung im Konstruktur aufgerufen.

## Zusammenfassung
Codebeispiel

#learning unit#