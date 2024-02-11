# Conditional modifiers
🎭

```swift
.foregroundColor(useRedText ? .red : .blue) //neu: foregroundStyle
```

Man kann das ganze auch mit einem `if` schreiben (ist aber nicht empfohlen). Aber es kommt in beiden Fällen auf das gleiche raus:

```swift
var body: some View {
    if useRedText {
        Button("Hello World") {
            useRedText.toggle()
        }
        .foregroundColor(.red) //neu: foregroundStyle
    } else {
        Button("Hello World") {
            useRedText.toggle()
        }
        .foregroundColor(.blue) //neu: foregroundStyle
    }
}
```

## Zusammenfassung
- Was bedeutet der Begriff?

#learning unit#