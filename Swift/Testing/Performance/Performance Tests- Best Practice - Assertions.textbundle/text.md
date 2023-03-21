# Performance Tests: Best Practice - Assertions
🏎️

## Best Practice: Assertions zum Test hinzufügen

- Man macht dass, um zu prüfen, ob die Testing-Bedingungen die gleichen geblieben sind.

- Wenn jemand hier zum Beispiel einen neuen Award hinzufügt, und der Performance-Test deswegen schlechter wird, dann sieht er gleich, was der Grund dafür ist.


```swift
func textXY() {
	createSampleData()
    let awards = Award.allAwards
    XCTAssertEqual(awards.count, 500, "This checks the awards count is constant. Change this if you add awards.")

	measure {
		//hier kommt der eigentliche Performance test, der mit den awards arbeitet.
	}
}
```

## Zusammenfassung
- In welchem Zusammenhang sollten bei Performance-Tests weitere Assertions hinzugefügt werden?


#learning unit#