# visualEffect Modifier
🎆

##  Zweck
- Damit kann man unabhängig von der Position der View einen visuellen Effekt erzielen
- Achtung: Nicht verwenden um Inhalt oder Layout zu verändern

## Beispiel

```swift
ForEach(0..<100) { i in
	Text("Hello \(i)")
		.font(.largeTitle)
		.frame(maxWidth: .infinity)
		.visualEffect { content, proxy in
			content.blur(radius: calculateScaleEffect(for: proxy))
		}
	}
}
```

Das Proxy wird verwendet, um die Position der einzelnen Elemente zu berechnen:

```swift
proxy.bounds(of: .scrollView)
```

Es gibt diverse Funktionen, die man dazu auf dem `content` aufrufen kann:

![][image-1]

## Resultat

![][image-2]

## Zusammenfassung
- Was kann man damit machen
- Welche zwei Parameter bekommt man?
- (ohne Berechnung der genauen Werte)

[image-1]:	assets/Bildschirmfoto%202023-06-17%20um%2019.35.45.png
[image-2]:	assets/2023-06-17%2019.37.35.gif

#learning unit# #iOS17