# Views
::1::

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


##  State initialisieren

```swift
@State var greeting: String
```

```swift
init() {
//wenn wir nur greeting schreiben würden dann hätte man ja gar keinen State wrapper. Mit _ schreiben wir in den State Wrapper. Man kann aber auch greeting ganz normal schreiben - dazu muss einfach die Variable bereits initialisiert sein.
    _greeting = new State<String>(initialValue: "Hello, World!")
}
```
