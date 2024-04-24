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

##  Fill / Stroke

###  Fill
```swift
Rectangle()
    .fill(Color.accentColor)
```
![][image-1]

###  Stroke

```swift
Rectangle()
    .stroke(Color.accentColor, lineWidth: 10)
```
![][image-2]

Siehe auch: [Shape Stroke Style][1]

##  Hinweis zur Grösse

Wenn man einer Shape keine grösse gibt, nimmt es automatisch den ganzen verfügbaren Platz ein

## Zusammenfassung
- Wir wird eine Shape erstellt? (allenfalls ohne den exakten Code)

[1]:	ulysses://x-callback-url/open?id=msQMWGb2G5Ry0cXVOjNndw

[image-1]:	assets/Bildschirmfoto%202024-04-16%20um%2009.53.54.png
[image-2]:	assets/Bildschirmfoto%202024-04-16%20um%2009.54.08.png

#learning unit#