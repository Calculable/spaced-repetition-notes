# Anchor Preferences
⚓️

## Um was geht es?
- Häufig verwendet man PreferenceKeys, um Informationen über das eigene Frame an den Parent zu geben.
- Mit Anchor Preferences geht dies noch einfacher.
- Siehe zuerst Kapitel: PreferenceKeyProtocol

## Was ist Anchor\<T\>

- Es ist entweder `Anchor<CGRect>` oder `Anchor<CGPoint>`

## Verwendung

```swift
Text(label)
	.padding(10)
	.anchorPreference(key: MyTextPreferenceKey.self, value: .bounds, transform: { [MyTextPreferenceData(viewIdx: self.idx, bounds: $0)] })
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
[https://swiftui-lab.com/communicating-with-the-view-tree-part-2/][1]

## Zusammenfassung
- Nur Konzept, keinen Code

[1]:	https://swiftui-lab.com/communicating-with-the-view-tree-part-2/

#learning unit#