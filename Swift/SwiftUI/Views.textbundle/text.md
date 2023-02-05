# Views 🌅

##  Beispiel
```swift
struct ContentView: View {
    @State private var tapCount = 0

    var body: some View {
        Button("Tap Count: \(tapCount)") {
            self.tapCount += 1
        }
    }
}
```

## Zusammenfassung
- Wie schreibt man eine View (mit State)
