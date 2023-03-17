# Learning: "Normale" View properties
🧠

## Beispiel

Hier wird ja nur gezeichnet, und nichts verändert, deshalb braucht man auch kein `@State`:

```swift
struct Checkerboard: Shape {
    let rows: Int
    let columns: Int
    
	func path(in rect: CGRect) -> Path {/*...*/}
}
```

`@State` bedeutet =\> We want to change it! - Ansonsten einfach Var verwenden, weil wenn sich der Wert ändert, wird die View sowieso neu gezeichnet...

## Zusammenfassung
- Weshalb kann man oft auf `@State` verzichten


#nur learning unit# #learning unit#