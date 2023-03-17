# Test throws
💥

> By marking the test method with  `throws`, we can use throwing code safely inside there – if any code throws without being handled by us, Xcode will consider the test to have failed.

- Wenn innerhalb einer Testing-Funktion ein Fehler geworfen wird, wird der Test als „fehlgeschlagen“ markiert.
		 
```swift
func testDeletingProjectCascadeDeletesItems() throws {
    try dataController.createSampleData()
}
```

## Zusammenfassung
- Was geschieht, wenn eine Text-Funktion einen Fehler wirft?

#nur learning unit# #learning unit#