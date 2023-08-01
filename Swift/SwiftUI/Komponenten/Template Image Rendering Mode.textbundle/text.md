# Template Image Rendering Mode
🟣

> Template mode renders all nontransparent pixels as the foreground color

```swift
Image("dot_green")
    .renderingMode(.original)
Image("dot_green")
    .renderingMode(.template)
```

![][image-1]

Jetzt kann man die Farbe der Symbols selbst anpassen:

```swift
Image("dot_green")
    .renderingMode(.template)
	.foregroundColor(.ubw_orange)
```

## Zusammenfassung
- Was kann man bei diesem Rendering Mode machen?

[image-1]:	https://docs-assets.developer.apple.com/published/872acc0f721844ccecf8b13d2f22f1dc/SwiftUI-Image-TemplateRenderingMode-dots@2x.png

#learning unit#