# Geometry Reader
📐

## Beispiel

```swift
GeometryReader { geo in
    Image("Example")
        .resizable()
        .scaledToFit()
        .frame(width: geo.size.width * 0.8)
}
```

![][image-1]

Beachte: Die Geometry-Reader View selbst nimmt immer den maximal verfügbaren Platz ein

## Globale Koordinaten

Bezogen auf den ganzen Bildschirm
```swift
geo.frame(in: .global).midX
```


##  Lokale Koordinaten

 Bezogen auf den unmittelbaren Parent
```swift
geo.frame(in: .local).midX
```

## Eigener Koordinaten-Space


```swift
OuterView()
	.background(.red)
    .coordinateSpace(name: "Custom")
```

```swift
geo.frame(in: .named("Custom")).midX
```


## Zusammenfassung
- Wie funktioniert GeoReader
- Wie kann man die Grösse auslesen
- Wie kann man absolute und relative Frame-Positionen auslesen?

[image-1]:	assets/Bildschirmfoto%202022-07-26%20um%2013.03.49.png

#learning unit# #guide