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


## Zusammenfassung
Codebeispiel