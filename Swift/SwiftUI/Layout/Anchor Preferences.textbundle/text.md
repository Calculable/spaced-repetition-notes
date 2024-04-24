# Anchor Preferences
⚓️

## Um was geht es?
- Häufig verwendet man PreferenceKeys, um Informationen über das eigene Frame an den Parent zu geben.
- Mit Anchor Preferences geht dies noch einfacher.
- Siehe zuerst Kapitel: [PreferenceKeyProtocol][1]

## Beispiel Anwendungsfall

Oder hier habe ich HStacks und VStacks verwendet und mit Preference Keys die Center der einzelnen Elemente ausgelesen, um dann das Overlay zu zeichnen.
![][image-1]

## Was ist Anchor\<T\>

- Es ist entweder `Anchor<CGRect>` oder `Anchor<CGPoint>`

## Verwendung

```swift
Text(label)
	.padding(10)
	.anchorPreference(key: MyPreferenceKey.self, value: .bounds, transform: { [MyTextPreferenceData(viewIdx: self.idx, bounds: $0)] })
```

- Beachte: Es braucht keinen Geometry Reader mehr
- Beachte: Man kann den Wert transformieren, damit er in die eigene Datenstruktur passt.
- Hier hätte `$0` den Typen `Anchor<CGRect>`
- Dies kann man jetzt wieder von einer Parent View auslesen: (siehe PreferenceKey Protokoll)

##  Einen Anchor in die Koordinaten konvertieren

Dazu verwendet man einen GeometryReader, damit es sich auf den aktuellen Coordinate Space bezieht:

```swift
.overlayPreferenceValue(MyCenterPreferenceKey.self) { centers in
		return GeometryReader { proxy in
			let convertedCenters = centers.map {
 				proxy[$0]
			}

			//Hier könnte man zum Beispiel mit einem Path das Custom drawing machen.
                            
       }
}
```

## Verschiedene Varianten

- bounds
- topLeading
- center
- bottom
- …

##  Mehrere Anchor Werte auf’s mal auslesen

Siehe:
[https://swiftui-lab.com/communicating-with-the-view-tree-part-2/][2]

## Zusammenfassung
- Nur Konzept, keinen Code: Wie ergänzen Anchor Preferences das PreferenceKey Protokoll?

[1]:	ulysses://x-callback-url/open?id=_UOqiYK7VeOg9VDOKLIOew
[2]:	https://swiftui-lab.com/communicating-with-the-view-tree-part-2/

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-05-11%20um%2016.37.23.png

#learning unit#