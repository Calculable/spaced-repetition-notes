# Decorator Pattern
🎗️

## Zweck

-  Sehr oft eingesetzt, vor allem bei Streams
- Man gibt einem Objekt neue Fähigkeiten, indem man es in ein Objekt ‚wrappt‘ (in den decorator)
- Man kann Objekte beliebig tief verschachteln

> Decorator can be recognized by creation methods or constructors that accept objects of the same class or interface as a current class.

## Praxisbeispiel mit Swift

Man wendet mehrere Filter auf ein Bild an:

```swift
let image = loadImage()

let resizerFitler = Resizer(image, xScale: 0.2)

let blurFilter = BlurFilter(resizer)
blurFilter.update(radius: 2)

let colorFilter = ColorFilter(blurFilter)
colorFilter.update(contrast: 0.53)

colorFilter.update(brightness: 0.12)
colorFilter.update(saturation: 4)

resizerFilter.apply()
```

## Zusammenfassung
- Zweck


#nur learning unit# #learning unit#