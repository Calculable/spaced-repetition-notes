# Learning: "Normale" View properties

## Beispiel

Hier wird ja nur gezeichnet, und nichts verändert, deshalb braucht man auch kein `@State`:

```swift
struct Checkerboard: Shape {
    let rows: Int
    let columns: Int
    
	func path(in rect: CGRect) -> Path {/*...*/}
}
```

## Zusammenfassung
- Weshalb kann man oft auf `@State` verzichten


#nur learning unit#