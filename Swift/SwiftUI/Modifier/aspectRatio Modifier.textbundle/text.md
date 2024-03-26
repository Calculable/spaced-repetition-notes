# .aspectRatio Modifier
🟦

## Beispiel: Eine View soll 16/9 sein

```swift
.aspectRatio(16/9, contentMode: .fit)
```
![][image-1]


##  Bei Bildern

```swift
Image("abc")
	.resizable()
	.aspectRatio(contentMode: .fit) //gleich wie scaledToFit()
```

![][image-2]

##  Was geschieht genau?

- Der AspectRatio Modifier bekommt vom Layout-System eine vorgeschlagene Grösse, ändert diese und gibt sie dann weiter.
- Die zurückgegebene Grösse des Systems ist jedoch die effektive grösse des Childs

Zum Beispiel hier:
```swift
Text("Hello, world")
    .aspectRatio(1, contentMode: .fit)
    .border(Color.accentColor)
```

Hier bekommt das Label eine Quadratische Grösse vorgeschlagen. Weil das Label jedoch nicht den ganzen Platz braucht, wird die effektive Grösse des Labels an das System zurück-reportet:

![][image-3]

## Quelle
[https://www.swiftuifieldguide.com/layout/aspect-ratio/][1]
##  Zusammenfassung

- Wie verwendet man den `.aspectRatio` Modifier?

[1]:	https://www.swiftuifieldguide.com/layout/aspect-ratio/

[image-1]:	assets/2024-03-23%2007.39.48.gif
[image-2]:	assets/2024-03-23%2007.40.12.gif
[image-3]:	assets/Bildschirmfoto%202024-03-23%20um%2007.45.29.png

#learning unit#