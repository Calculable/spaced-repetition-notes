# .safeAreaInset() Modifier
📱

## Code

- Ein Modifier für ScrollView, List und Form
- Damit kann man weitere Elemente vor und nach bzw. über eine Liste, Form oder Scroll View hängen


```swift
List(0..<100) { i in
    //...
}
.safeAreaInset(edge: .bottom, alignment: .trailing) {
	//help button
}
```


## Screenshot
![][image-1]

Ein weiterer Vorteil: Wenn eine Tastatur angezeigt wird, rutscht es nach oben:

![][image-2]


##  Zusammenfassung
- Wozu ist dieser Modifier gut?

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-03-30%20um%2008.23.36.png
[image-2]:	assets/DraggedImage.png

#learning unit#