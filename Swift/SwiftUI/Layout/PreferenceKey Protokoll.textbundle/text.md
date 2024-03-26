# PreferenceKey Protokoll
🧐
## Quelle
Quelle: [https://swiftui-lab.com/communicating-with-the-view-tree-part-1/][1]

## Um was geht es?
- Man kann von oben in der Hierarchie auf die Werte unten in der Hierarchie zugreifen
- Mit **anchored preferences** kann man Geometrie-Informationen der Child-Views auslesen

## Zwei Arten um die Keys auszulesen
- **onPreferenceChange**: Hier kann man die Infos zum Beispiel speichern und so eine UI-Veränderung auslösen (Vorsicht vor Endlosschleife!)
- **backgroundPreferenceValue**: Hier kann man die Infos direkt zum Zeichnen verwenden)

## Beispiel Anwendungsfall
- Die NavigationView bekommt von einer View unterhalb den `navigationBarTitle()`

Oder hier habe ich HStacks und VStacks verwendet und mit Preference Keys die Center der einzelnen Elemente ausgelesen, um dann das Overlay zu zeichnen.
![][image-1]

## Preference Key definieren

```swift
struct MyTextPreferenceData: Equatable {
    let viewIdx: Int
    let rect: CGRect
}
```

```swift
struct MyTextPreferenceKey: PreferenceKey {
    typealias Value = [MyTextPreferenceData]

    static var defaultValue: [MyTextPreferenceData] = []
    
    static func reduce(value: inout [MyTextPreferenceData], nextValue: () -> [MyTextPreferenceData]) {
        value.append(contentsOf: nextValue())
    }
}
```

Die `reduce`-Funktion ist dazu da, um alle Werte zu kombinieren, die auf dem View Tree gefunden wurden. Hier wird einfach ein Array daraus gemacht.

Beachte: Die Werte werden in view-tree-order geliefert.

## Preference Key verwenden

```swift
Rectangle()
	.fill(Color.clear)
	.preference(key: MyTextPreferenceKey.self, value: [myData])
```

## Werte vom Geometry Reader auslesen
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

=\> Eine Elegantere Lösung: `Anchor Preferences` (siehe separates Kapitel)


##  Vorsicht vor Endlos-Schleifen

>  if the ancestor reacts to changes in the layout of a child, and the child reacts to the changes of the ancestor.

- Wenn man bei jeder Frame-Änderung den Parent über den PreferenceKey informiert, muss man aufpassen, dass der Parent nicht anschliessend das Layout ändert, und so eine Endlosschleife auslöst.

Lösungen: `ZStack, .overlay(), .background(), GeometryEffect`

## Auf Preference Changes reagieren

```swift
.onPreferenceChange(MyTextPreferenceKey.self) { preferences in
    for p in preferences {
        self.rects[p.viewIdx] = p.rect
    }
}
```

##  Noch einfacher auf Preferences reagieren:

- Hier kann man direkt im Hintergrund zeichnen und auf die Werte zugreifen
```swift
myCustomView 
	.backgroundPreferenceValue(MyCenterPreferenceKey.self) { preferenceValue in
    	//Hier könnte man zum Beispiel mit Path etwas zeichnen
	}
```

- Alternativ gibt es auch `.overlayPreferenceValue()`

##  Alternative
- Alternativ würde man jede Child-View in einen Geometry Reader wrappen und die Informationen über die Grösse über ein Binding wieder an die Parent-View geben. Das ist aber relativ unschön.

##  Zusammenfassung
- Was ist die Idee
- Konzeptionell: Welche zwei Arten gibt es, um die Keys auszulesen (ohne Code)

[1]:	https://swiftui-lab.com/communicating-with-the-view-tree-part-1/

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-05-11%20um%2016.37.23.png

#learning unit#