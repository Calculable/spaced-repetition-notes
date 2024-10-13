# SwiftUI Layout: 3 Schritte
🟪

## Drei Schritte

- A parent view proposes a size for its child.
- Based on that information, the child then chooses its own size and the parent must respect that choice.
- The parent then positions the child in its coordinate space.

=\> Mit Geometry-Reader kann man die vorgeschlagene Grösse auslesen.

## Beispiel: Man hat das folgende Layout

```java
struct ContentView: View {
    var body: some View {
        Text("Hello, World!")
			.padding()
            .background(.red)
    }
}
```

Beachte: Background ist eigentlich der Parent von Padding und Padding ist der Parent von Text...

Jetzt läuft es folgendermassen ab: 

- Swift UI geht zum ContentView und sagt: „du hast den ganzen Platz zur Verfügung, wie viel brauchst du?“ 
- Die Content View fragt den Background
- Der Background fragt das Padding
- Das Padding zieht 32 von der Vorgeschlagenen grösse ab und fragt damit den Text
- Der Text gibt seine Intrinsic Content Size zurück
- Das Padding rechnet auf die zurückgegebene Grösse 32 Dazu
- Diese Grösse wird dann vom Background verwendet
- Weil der Background nicht die gesamte Grösse einnimmt kann die ContentView den Background positionieren (Standartmässig in der Mitte des Screens)

![][image-1]

**Beachte**: Wenn man einen Modifier auf ein Element anwendet, dann ist das Element am Ende eigentlich ein Child des Modifiers (vom Rückgabewert her). Deshalb fragt die ContentView auch zuerst den Background und nicht den text. Nicht vergessen: Wenn man auf eine View einen Modifier anwendet, dann ist das Resultat eine andere View.


> Views have very different behaviors when it comes to proposing and reporting. For example, a regular image view ignores the proposed size but returns its intrinsic size. An aspect ratio modifier can propose twice to its child — once to figure out the underlying aspect ratio and once to actually render the child. A shape such as a rectangle unconditionally accepts the proposed size. Understanding how different views respond to proposed sizes is essential for building complex layouts. There are no requirements on the response: a view can accept, ignore or do something else with the proposed size.

##  Quelle
[https://www.swiftuifieldguide.com/layout/introduction/][1]

## Zusammenfassung
- Nach welchen 3 Regeln werden die UI’s aufgebaut?

[1]:	https://www.swiftuifieldguide.com/layout/introduction/

[image-1]:	assets/Bildschirmfoto%202024-03-23%20um%2007.12.31.png

#learning unit# #guide