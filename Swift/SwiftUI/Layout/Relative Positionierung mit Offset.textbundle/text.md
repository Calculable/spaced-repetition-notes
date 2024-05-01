# Relative Positionierung mit Offset
📍

- Mit Offset-Modifier

```java
var body: some View {
    Text("Hello, world!")
        .offset(x: 100, y: 100)
        .border(Color.black, width: 1)
}
```

![][image-1]

Beachte: Das restliche Layout wird nicht beeinflusst. Das macht es besonders sinnvoll für Animationen

## Zusammenfassung
- Wie positioniert man eine View relativ?

[image-1]:	assets/Bildschirmfoto%202024-03-23%20um%2007.52.27.png

#learning unit#