# Override Properties
🖋️

- Man kann nur Computed Properties overriden, keine Stored Properties!


```swift
class Vehicle {
	var speed: Int {
		return 500
	}
}

class Car: Vehicle {
	override var speed: Int {
		return 1000
	}
}
```

## Zusammenfassung
- Welche Properties können überschrieben werden?
- Wie überschreibt man eine Property aus der Oberklasse?


#learning unit#