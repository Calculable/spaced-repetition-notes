# Foreground Style
🌈

- Ersetzt den `.foregroundColor` Modifier
- Nimmt ein beliebiger ShapeStyle entgegen

```swift
Image(systemName: "triangle.fill")
	.foregroundStyle(myColor)
```
![][image-1]


```swift
Text("Gradient Text")
    .font(.largeTitle)
    .foregroundStyle(
        .linearGradient(
            colors: [.yellow, .blue],
            startPoint: .top,
            endPoint: .bottom
        )
    )
```
![][image-2]

## Zusammenfassung
- Was nimmt .foregroundStyle für einen Parameter entgegen?

[image-1]:	assets/View-foregroundStyle-1@2x%20Kopie.png
[image-2]:	https://docs-assets.developer.apple.com/published/b16bb501b642dd7afbb6fb266ef4cffc/View-foregroundStyle-2@2x.png

#learning unit#