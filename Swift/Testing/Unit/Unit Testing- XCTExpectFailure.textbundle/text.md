# Unit Testing: XCTExpectFailure
👁️‍🗨️

Man weiss das ein Test fehlschlägt, aber man will es trotzdem einchecken:

```swift
func testAddFavorite() throws {
	XCTExpectFailure("First item in the favorites set is not always the first smoothie we added (tracked by issue://987654321)", strict: false)

	//Rest of the failing test
}
```

Achtung: Das ist nicht das gleiche wie XCTAssertThorwsError!


## Zusammenfassung
- Code
- Warum braucht man das?


#learning unit#