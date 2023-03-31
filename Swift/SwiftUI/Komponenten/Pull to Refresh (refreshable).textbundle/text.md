# Pull to Refresh (refreshable)
⬇️

```swift
struct ContentView: View {
    @State private var numbers = [String]()

    var body: some View {
        List(0..<numbers.count, id: \.self) { i in
            Text(numbers[i])
        }
        .refreshable(action: rollDice)
    }

    func rollDice() {
        let result = Int.random(in: 1...6)
        numbers.append(String(result))
    }
}

```

##  Zusammenfassung
- Code

#learning unit#