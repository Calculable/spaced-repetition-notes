# Map für Optional 
🗺️

- Man erspart sich den Check auf `nil`
- Wenn es einen Wert drin hat, so wird dieser transformiert
- Wenn nicht, bleibt es `nil`

```swift
.foregroundColor(viewModel.color.map { Color($0) } ?? .clear)
```

## Zusammenfassung
- Wie kann man Map in Kombination mit `nil` verwenden?