# Shape
🍏

## Beispiel
```swift
struct Triangle: Shape {
    func path(in rect: CGRect) -> Path {
        var path = Path()

        path.move(to: CGPoint(x: rect.midX, y: rect.minY))
        path.addLine(to: CGPoint(x: rect.minX, y: rect.maxY))
        path.addLine(to: CGPoint(x: rect.maxX, y: rect.maxY))
        path.addLine(to: CGPoint(x: rect.midX, y: rect.minY))

        return path
    }
}
```

Jetzt kann man es zum Beispiel so verwenden:

```swift
Triangle()
    .fill(.red)
    .frame(width: 300, height: 300)
```

##  Hinweis zur Grösse

Wenn man einer Shape keine grösse gibt, nimmt es automatisch den ganzen verfügbaren Platz ein

## Zusammenfassung
- Wir wird eine Shape erstellt? (allenfalls ohne den exakten Code)

#learning unit#