# UI Tests
👆


## Beispiel
```swift
app.buttons["Open"].tap()
```

## Wie funktionieren Queries

- Hier sind zwei Beispiele:

```swift
app.buttons["Open"]
```

```swift
app.tabBars.buttons
```

- Beachte: Man schreibt immer plural. 
- Wenn es jedoch nur ein Element gibt, dass auf die Query matcht, kann man direkt damit arbeiten.
- Es wird immer nur im sichtbaren Teil des Bildschirms gesucht
- Im Hintergrund funktioniert das UI-Testing über das Accessibility System. Das heisst zum Beispiel: Wenn man einen `+` Button hat, der im Accessibility-System jedoch "Add" heisst, kann man ihn so finden: `app.buttons["add"]`


## Beispiel: Details

```swift
func testEditingProjectUpdatesCorrectly() {
    app.buttons["Open"].tap()

	//Status vorher
    XCTAssertEqual(app.tables.cells.count, 0, "There should be no list rows initially.")

	//Aktion
    app.buttons["add"].tap()

	//Status nachher
    XCTAssertEqual(app.tables.cells.count, 1, "There should be 1 list row after adding a project.")
}
```

- Beachte: Es ist ein gängiges Muster, jeweils den Status vor der Aktion und den Status nach der Aktion zu prüfen
- Beachte: Hier werden mehrere Asserts gleichzeitig eingesetzt.


## Zusammenfassung
- Beispiel: Den Button („Open“) klicken


#learning unit#