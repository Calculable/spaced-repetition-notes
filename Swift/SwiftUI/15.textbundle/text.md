# Path 🖊️
::15::

```swift
Path { path in
    path.move(to: CGPoint(x: 200, y: 100))
    path.addLine(to: CGPoint(x: 100, y: 300))
    path.addLine(to: CGPoint(x: 300, y: 300))
    path.addLine(to: CGPoint(x: 200, y: 100))
	//path.closeSubpath() -> braucht man bei diesem Stroktstyle nicht...
}
.fill(.blue)
//.stroke(.blue, style: StrokeStyle(lineWidth: 10, lineCap: .round, lineJoin: .round))
```

(entweder fill oder stroke…)
![][image-1]

## Zusammenfassung
- Wie wird Path verwendet?

[image-1]:	assets/Bildschirmfoto%202022-07-27%20um%2015.59.22.png