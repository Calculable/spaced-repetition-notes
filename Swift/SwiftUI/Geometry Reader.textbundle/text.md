# Geometry Reader 📐

## Beispiel

```swift
GeometryReader { geo in
    Image("Example")
        .resizable()
        .scaledToFit()
        .frame(width: geo.size.width * 0.8)
}
```

Beachte: Die Geometry-Reader View selbst nimmt immer den maximal verfügbaren Platz ein:

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

## Zusammenfassung
- Wie funktioniert GeoReader
- Wie kann man die Grösse auslesen
- Wie kann man absolute und relative Positionen auslesen?