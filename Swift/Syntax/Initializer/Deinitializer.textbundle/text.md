# Deinitializer
❌

Wird aufgerufen, bevor das Objekt durch die Speicherverwaltung entfernt wird:

```swift
class AClass {
	var a = "abc"

	deinit {
		print("deinit was called")
	}
}
```

##  Zusammenfassung
- Syntax
- Wann wird es aufgerufen?

#learning unit#