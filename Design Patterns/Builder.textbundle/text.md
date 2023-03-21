# Builder
🚧

##  Zweck
- Um grosse Konstruktoren verhindern

## Beispiel
- Eine Order besteht aus mehreren Gängen. Anstatt alle Gänge im Konstruktor zu setzen, macht man folgendes:

```swift
let builder = OrderBuilder()
builder.reset()
builder.setMainCourse(steak)
builder.setGarnish(chips)
builder.setDrink(coffee)
let order = builder.create()
```

So ist das ganze implementiert:

```swift
// Builder
class OrderBuilder {
	private var order: Order?
	
	func reset() {
		order = Order()
	}

	func setFirstCourse(_ dish: Dish) {
		///
	}


	func setMainCourse(_ dish: Dish) {
		//...
	}

	func create() -> Order? {
		return order ?? nil
	}
}
```

## Zusammenfassung
- Zweck
- Beispiel-Code

#learning unit#