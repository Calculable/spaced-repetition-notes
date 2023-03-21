# Tests kommentieren: Best Practice
✍️

- Häufig verwendet man bei Tests relative lange Funktionsnamen
- Häufiges Muster: “given, when, then” 
-  Beispiel:

```swift
func testBindingOnChangeCallsFunction() {
    // Given
    var onChangeFunctionRun = false

    func exampleFunctionToCall() {
        onChangeFunctionRun = true
    }

    var storedValue = ""

    let binding = Binding(
        get: { storedValue },
        set: { storedValue = $0 }
    )

    let changedBinding = binding.onChange(exampleFunctionToCall)

    // When
    changedBinding.wrappedValue = "Test"

    // Then
    XCTAssertTrue(onChangeFunctionRun, "The onChange() function was not run.")
}
```


## Zusammenfassung

Nach welchem Muster werden Tests häufig korrigiert?




#learning unit#