# Super Initializer
🛫

## Super Initializer aufrufen
Wenn man kein `override` schreibt UND der Super-Konstruktor keine Argumente hat, wird der Super-Initializier Implizit aufgerufen:
```swift
init(color: String) {
	self.color = color
	// super.init() implicitly called here
}
```

Wenn man `override` schreibt, wird der Super-Initializier explizit aufgerufen:

```swift
 override init() {
	super.init()
	numberOfWheels = 2
}
```



## Zusammenfassung
Wann wird der super-init aufgerufen?

#learning unit#