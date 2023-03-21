# Layout: 3 Schritte
🟪

## Three Steps

- A parent view proposes a size for its child.
- Based on that information, the child then chooses its own size and the parent must respect that choice.
- The parent then positions the child in its coordinate space.

=\> Mit Geometry-Reader kann man die vorgeschlagene Grösse auslesen.

## Beispiel: Man hat das folgende Layout

```java
struct ContentView: View {
    var body: some View {
        Text("Hello, World!")
            .background(.red)
    }
}
```

Jetzt läuft es folgendermassen ab: Swift UI geht zum ContentView und sagt: „du hast den ganzen Platz zur Verfügung, wie viel brauchst du?“ Das ContentView Fragt den Background, der Background Fragt den Text. Und der Text hat die definitive Antwort wie gross es sein muss.

Swift UI weiss jetzt also, dass ContentView nicht den ganzen Platz benötigt. Swift UI kann entscheiden, wo es das Child platziert. On diesem Beispiel wird das Child in der Mitte des Screens platziert

![][image-1]

**Beachte**: Wenn man einen Modifier auf ein Element anwendet, dann ist das Element am Ende eigentlich ein Child des Modifiers (vom Rückgabewert her). Deshalb fragt die ContentView auch zuerst den Background und nicht den text. Nicht vergessen: Wenn man auf eine View einen Modifier anwendet, dann ist das Resultat eine andere View.


## Zusammenfassung
- Nach welchen 3 Regeln werden die UI’s aufgebaut?

[image-1]:	assets/Bildschirmfoto%202022-08-21%20um%2011.58.13.png

#learning unit#