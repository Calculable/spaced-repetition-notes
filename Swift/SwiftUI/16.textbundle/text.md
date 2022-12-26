# Shape
::16::

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


## Hinweis zu Winkeln und Koordinaten
> In the eyes of SwiftUI 0 degrees is not straight upwards, but instead directly to the right.

> Shapes measure their coordinates from the bottom-left corner rather than the top-left corner, which means SwiftUI goes the other way around from one angle to the other. This is, in my not very humble opinion, extremely alien.
