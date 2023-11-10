# Initializer: Reihenfolge der Statements
🛫

```swift
 init(sideLength: Double, name: String) {
	self.sideLength = sideLength //set subclass-properties
	super.init(name: name) //superclass initializer
	numberOfSides = 3 //change superclass
	//additional setup with methods, getters, setters...
}
```

## Zusammenfassung

In welcher Reihenfolge kommen die Statements im Initializer?

- additional setup with methods, getters, setters...
- set properties
- superclass initializer
- change superclass

#learning unit#