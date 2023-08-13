# View abchneiden
✂️

Das obere Ende einer View abschneiden:

```swift
YourView()
    .frame(height: 85, alignment: .topLeading)
    .clipped()
```

aus der Dokumentation:

> "clipped" clips this view to its bounding rectangular frame.

## Zusammenfassung
- Wie kann man eine View abschneiden, so dass nur die ersten 85 Pixel gezeichnet werden?

#learning unit#