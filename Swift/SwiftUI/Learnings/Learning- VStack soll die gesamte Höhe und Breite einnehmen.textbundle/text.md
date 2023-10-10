# Learning: VStack soll die gesamte Höhe und Breite einnehmen
🧠

##  Problem

Der Text erscheint in der Mitte der View statt an der „leading“ Kante. 

```swift
VStack(alignment: .leading) {
	Text("Hello")
}
```

## Ursache

Der VStack selbst ist zwar korrekt ausgerichtet, nimmt aber selbst nicht den ganzen verfügbaren Platz ein:

## Lösung
```swift
VStack(alignment: .leading) {
    Text("Hello")
}.frame(maxWidth: .infinity, maxHeight: .infinity, alignment: .topLeading)
```

![][image-1]

## Quelle:
[https://stackoverflow.com/questions/56487323/make-a-vstack-fill-the-width-of-the-screen-in-swiftui][1]


[1]:	https://stackoverflow.com/questions/56487323/make-a-vstack-fill-the-width-of-the-screen-in-swiftui

[image-1]:	assets/Bildschirmfoto%202023-07-27%20um%2013.14.14.png

#learning unit#