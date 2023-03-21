# Conditional modifiers
🎭

```swift
.foregroundColor(useRedText ? .red : .blue)
```

Man kann das ganze auch mit einem `if` schreiben (ist aber nicht empfohlen). Aber es kommt in beiden Fällen auf das gleiche raus:

```swift
var body: some View {
    if useRedText {
        Button("Hello World") {
            useRedText.toggle()
        }
        .foregroundColor(.red)
    } else {
        Button("Hello World") {
            useRedText.toggle()
        }
        .foregroundColor(.blue)
    }
}
```

## Zusammenfassung
- Was bedeutet der Begriff?

#learning unit#