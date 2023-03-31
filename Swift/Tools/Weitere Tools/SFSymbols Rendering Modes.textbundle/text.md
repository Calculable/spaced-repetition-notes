# SFSymbols Rendering Modes
♠️

## 4 Rendering Modes

![][image-1]

=\> Jedes Symbol hat einen anderen „Default“ Modus

## Monochrome (Default)

```swift
            Image(systemName: "cloud.sun.rain.fill")
                .foregroundStyle(.blue)
                .font(.system(size: 144))
```

![][image-2]

## Hierarchical

Aus einer einzigen Farbe werden die anderen abgeleitet:

```swift
Image(systemName: "cloud.sun.rain.fill")
    .symbolRenderingMode(.hierarchical)
    .foregroundStyle(.blue)
    .font(.system(size: 144))
```

![][image-3]

So kann man zum Beispiel eine Art Vortschrittsanzeige machen:



## Palette

```swift
Image(systemName: "cloud.sun.rain.fill")
    .symbolRenderingMode(.palette)
    .foregroundStyle(.blue, .red)
    .font(.system(size: 144))
```

![][image-4]

## Multicolor

- Hier hat man die Objekte in ihrer „natürlichen“ Farbe

```swift
Image(systemName: "cloud.sun.rain.fill")
    .symbolRenderingMode(.multicolor)
    .font(.system(size: 144))
```

![][image-5]

## Zusammenfassung
- Welche 4 Rendering Modes für SFSymbole gibt es und wie verwendet man sie?

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-03-17%20um%2016.59.35.png
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-03-28%20um%2015.34.20.png
[image-3]:	assets/Bildschirm%C2%ADfoto%202023-03-28%20um%2015.34.36.png
[image-4]:	assets/Bildschirm%C2%ADfoto%202023-03-28%20um%2015.36.13.png
[image-5]:	assets/Bildschirm%C2%ADfoto%202023-03-28%20um%2015.36.40.png

#learning unit#