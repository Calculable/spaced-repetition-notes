# PreferenceKey Protokoll
🧐
## Quelle
Quelle: [https://swiftui-lab.com/communicating-with-the-view-tree-part-1/][1]

## Um was geht es?
- Man kann von oben in der Hierarchie auf die Werte unten in der Hierarchie zugreifen
- Mit **[anchored preferences][2]** kann man Geometrie-Informationen der Child-Views auslesen
- Beispiel: Die NavigationView bekommt von einer View unterhalb den `navigationBarTitle()`

## Eigenen Preference Key definieren

```swift
struct MyTitleData: Equatable {
    let viewId: String
    let text: String
}

struct MyTitlePreferenceKey: PreferenceKey {
    typealias Value = [MyTitleData]

    static var defaultValue: [MyTitleData] = []

    static func reduce(value: inout [MyTitleData], nextValue: () -> [MyTitleData]) {
        value.append(contentsOf: nextValue())
    }
}
```

Die `reduce`-Funktion ist dazu da, um alle Werte zu kombinieren, die auf dem View Tree gefunden wurden. Hier wird einfach ein Array daraus gemacht. Man kann aber zum Beispiel auch das Maximum aller Werte nehmen etc.

Beachte: Die Werte werden in view-tree-order geliefert.

## Beispiel

![][image-1]

```swift
struct ContentView: View {

    @State var titles: [MyTitleData] = []

    var body: some View {

        VStack {
            ForEach(titles, id: \.viewId) { title in
                Text("View \(title.viewId) has title \(title.text)")
            }

            Subviews()
        }
        .onPreferenceChange(MyTitlePreferenceKey.self) { titles in
            self.titles = titles
        }

    }

}

struct Subviews: View {
    var body: some View {

        VStack {
            Rectangle()
                .fill(Color.red)
                .preference(key: MyTitlePreferenceKey.self, value: [.init(viewId: "Red Rectangle", text: "Title 1")])

            Rectangle()
                .fill(Color.green)
                .preference(key: MyTitlePreferenceKey.self, value: [.init(viewId: "Green Rectangle", text: "Title 2")])
        }

    }
}
```

## Tipp: Werte vom Geometry Reader auslesen
Meistens gibt man hier die Werte eines Geometry readers zurück. Damit der Geometry Reader aber nicht den gesamten Platz einnimmt, wird häufig ein Geometry Reader innerhalb einer `.background`-Property verwendet:

```
myView
    .background(GeometryReader { geometry in
    Color.clear.preference(
        key: ButtonWidthPreferenceKey.self,
        value: geometry.size.width
    )
})
```

=\> Eine Elegantere Lösung: **[anchored preferences][3]**  (siehe separates Kapitel)


##  Hinweis: Vorsicht vor Endlos-Schleifen

>  if the ancestor reacts to changes in the layout of a child, and the child reacts to the changes of the ancestor.

- Wenn man bei jeder Frame-Änderung den Parent über den PreferenceKey informiert, muss man aufpassen, dass der Parent nicht anschliessend das Layout ändert, und so eine Endlosschleife auslöst.

Lösungen: `ZStack, .overlay(), .background(), GeometryEffect`...

## Auf Preference Changes reagieren

###  Variante 1: onPreferenceChange

- Wie im Beispiel von oben

```swift
.onPreferenceChange(MyTextPreferenceKey.self) { preferences in
    for p in preferences {
        self.rects[p.viewIdx] = p.rect
    }
}
```

### Variante 2: backgroundPreferenceValue / overlayPreferenceValue

- Wenn man die Preferences verwendet, um etwas zu zeichnen, kann man diese Variante verwenden weil man so keinen State in der View speichern muss
- Hier kann man direkt im Hintergrund zeichnen und auf die Werte zugreifen
```swift
myCustomView 
	.backgroundPreferenceValue(MyCenterPreferenceKey.self) { preferenceValue in
    	//Hier könnte man zum Beispiel mit Path etwas zeichnen
	}
```

##  Alternative
- Alternativ würde man jede Child-View in einen Geometry Reader wrappen und die Informationen über die Grösse über ein Binding wieder an die Parent-View geben. Das ist aber relativ unschön.

##  Zusammenfassung
- Was ist die Idee
- Konzeptionell: Welche zwei Arten gibt es, um auf preferences bzw. Änderungen der Preferences zu reagieren?

[1]:	https://swiftui-lab.com/communicating-with-the-view-tree-part-1/
[2]:	ulysses://x-callback-url/open?id=71hYRQFgoMrZ8V7RWOPiZA
[3]:	ulysses://x-callback-url/open?id=71hYRQFgoMrZ8V7RWOPiZA

[image-1]:	assets/Bildschirmfoto%202024-04-05%20um%2008.35.06.png

#learning unit#