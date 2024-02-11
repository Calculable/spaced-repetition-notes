# Template Image Rendering Mode - Bilder einfärben
🟣

> Template mode renders all nontransparent pixels as the foreground color

![][image-1]

```swift
Image("dot_green")
    .renderingMode(.original)
Image("dot_green")
    .renderingMode(.template)
```

![][image-2]

Jetzt kann man die Farbe der Symbols selbst anpassen:

```swift
Image("dot_green")
    .renderingMode(.template)
	.foregroundColor(.ubw_orange) //neu: foregroundStyle
```

Man kann es auch direkt in XCode definieren:

![][image-3]

Siehe auch UIKit-Variante: [ulysses://x-callback-url/open?id=149hkrH35zYj88XiIyWpOg][1]


## Zusammenfassung
- Was kann man bei diesem Rendering Mode machen?

[1]:	ulysses://x-callback-url/open?id=149hkrH35zYj88XiIyWpOg

[image-1]:	assets/Bildschirmfoto%202024-02-01%20um%2007.13.08.jpeg
[image-2]:	https://docs-assets.developer.apple.com/published/872acc0f721844ccecf8b13d2f22f1dc/SwiftUI-Image-TemplateRenderingMode-dots@2x.png
[image-3]:	assets/Bildschirmfoto%202023-10-25%20um%2012.30.21.png

#learning unit#