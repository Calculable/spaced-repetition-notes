# Testing mit externen Ressourcen
💾

## Files zum Test-Target hinzufügen

- Man kann die Files einfach in eine Untergruppe der Testing-Gruppe ablegen.

## Files laden

- Man kann es nicht mit `Bundle.main` laden. Stattdessen kann man das Bundle suchen, dass am gleichen Ort wie eine Klasse ist:

```swift
func testDecodingString() {
    let bundle = Bundle(for: MyTestFile.self)
	//use bundle to access resources
}
```

## Zusammenfassung
- Wie greift man auf das Testing Bundle zu?

#learning unit#