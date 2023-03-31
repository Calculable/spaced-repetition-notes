# Ein Sheet nicht Bildschirmfüllend machen
🪟

```swift
Button("Show Sheet") {
    showingSheet = true
}.sheet(isPresented: $showingSheet) {
    Text("Hello, i am the sheet content")
        .presentationDetents([.medium, .large])
}
```

![][image-1]

## Zusammenfassung
- Wie macht man ein Sheet, welches nicht die ganze Höhe einnimmt?

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-03-30%20um%2008.56.21.png

#learning unit#