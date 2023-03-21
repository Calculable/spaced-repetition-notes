# View State: Custom Initializer
🎛️

##  Beispiel
```swift
@State private var tapCount = 0
```

##  State initialisieren

Nicht empfohlen

```swift
@State var greeting: String
```

```swift
init() {
//wenn wir nur greeting schreiben würden dann hätte man ja gar keinen State wrapper. Mit _ schreiben wir in den State Wrapper. Man kann aber auch greeting ganz normal schreiben - dazu muss einfach die Variable bereits initialisiert sein.
    _greeting = new State<String>(initialValue: "Hello, World!")
}
```

## Zusammenfassung
- Wie macht man einen Initializer für den View State (nicht empfohlen)


#learning unit#