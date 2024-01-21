# Custom Modifier
🖌️

## Definieren

```swift
struct Title: ViewModifier {
    func body(content: Content) -> some View {
        content
            .font(.largeTitle)
            .foregroundColor(.white)
            .padding()
            .background(.blue)
            .clipShape(RoundedRectangle(cornerRadius: 10))
    }
}
```

## Anwenden

```swift
Text("Hello World")
    .modifier(Title())
```

## Anwendung vereinfachen mit einer Extension

```swift
extension View {
    func titleStyle() -> some View {
        modifier(Title())
    }
}
```

```swift
Text("Hello World")
    .titleStyle()
```

## Zusammenfassung
- Wie schreibt man einen Custom Modifier? (Nur konzeptionell, nicht den genauen code)

#learning unit#