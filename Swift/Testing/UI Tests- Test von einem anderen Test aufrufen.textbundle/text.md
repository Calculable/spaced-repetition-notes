# UI Tests: Test von einem anderen Test aufrufen
👆

Oftmals macht man bei UI-Tests mehrfach das gleiche, um zu einer bestimmten Stelle im App zu gelangen.

Ist dies der Fall, kann man aus einem Test heraus einen anderen Test aufrufen:


```swift
func testEditingItemUpdatesCorrectly() {
	//other code

	// Go to Open Projects and add one project and one item.
	testAddingItemInsertsRows()
	
	// other code
}
```

## Diskussion

- Man sollte es Kommentieren, damit klar ist was geschieht
- Normalerweise sollten Tests nicht aufeinander aufbauen!
- In diesem Fall ist das jedoch nicht so schlecht, weil die Tests unabhängig voneinander laufen zwischen zwei Test-Vorgängen.

## Zusammenfassung
- Wie schreibt man aufbauende UI tests?
- Wann ist das ok?

#nur learning unit# #learning unit#