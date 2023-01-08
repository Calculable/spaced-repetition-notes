# Observed Properties ℹ️
::11.2::

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


## Zusammenfassung
Codebeispiel