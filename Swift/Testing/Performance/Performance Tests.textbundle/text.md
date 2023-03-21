# Performance Tests
👁️‍🗨️

Measure-Tests werden automatisch mehrmals gestartet, um Schwankungen zu vermeiden. 

Interessant ist auch dass man messen kann, wie sich die Performance mit der Zeit verändert.

```swift
func testPerformanceExample() {
    let generator = ImageGenerator()

    measure {
        generator.generateImages()
    }
}
```

## Zusammenfassung
- Beispiel


#learning unit#