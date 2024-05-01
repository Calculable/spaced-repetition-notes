# SwiftUI Z-Index

## Beschreibung
- Zwischen 0 und 1000
- Standartmässig auf 0

Achtung, man kann nur Ebene auf der gleichen Hierarchie-Stufe mit dem z-Index neu umsortieren:


## Ausgangslage

```swift
HStack {
    VStack {
        Color.red
            .offset(x: 50, y: 50)
            .opacity(0.95)
        Color.blue
            .offset(x: 50, y: -50)
            .opacity(0.95)
    }
    VStack {
        Color.yellow
            .offset(x: -50, y: 50)
            .opacity(0.95)
        Color.green
            .offset(x: -50, y: -50)
            .opacity(0.95)
    }
}
```

![][image-1]

## Mit Z-Index
- Rot ist zwar höher als Blau, aber nicht höher als gelb:

```swift
HStack {
    VStack {
        Color.red
            .offset(x: 50, y: 50)
            .zIndex(2.0)
        Color.blue
            .offset(x: 50, y: -50)
    }
    VStack {
        Color.yellow
            .offset(x: -50, y: 50)
            .zIndex(1.0)
        Color.green
            .offset(x: -50, y: -50)
    }
}
```
![][image-2]

##  Zusammenfassung
- Wie verhält sich der Z-Index auf verschiedenen Hierarchiestufen?
- Welche Werte sind als Z-Index möglich?

[image-1]:	assets/Bildschirmfoto%202024-04-09%20um%2020.24.53.png
[image-2]:	assets/Bildschirmfoto%202024-04-09%20um%2020.24.10.png

#learning unit#