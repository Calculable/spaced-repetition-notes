# LabeledContent

## Zweck und Code
Besonders hilfreich für Controls, welche kein eigenes Label haben:

```swift
LabeledContent {
	Slider(value: $brightness)
} label: {
	Text("Brightness")
}
```
Hinweis: Wird auf iOS anders dargestellt als auf macOS.

Das ist besonders sinnvoll für macOS, wo einige Views ihren eigenen Titel nicht anzeigen


![][image-1]

## Als alternative zu Badge
Wenn man es nur mit Text verwendet, verhaltet es sich ählich wie ein Badge:

```swift
 LabeledContent("This is important", value: "Value goes here")
```

![][image-2]

##  Titel und Subtitel

Man kann mehrere Labels übergeben, diese werden dann hierarchisch gerendert:

```swift
LabeledContent {
    Text("Value")
} label: {
    Text("Title")
    Text("Subtitle")
    Text("Subsubtitle")
    Text("Subsubsubtitle")
}
```


![][image-3]


## Accessibility Hinweis

- Aktuell verwenden einige Views den Titel des LabeledContent nicht für Voice Over!

##  Zusammenfassung
- Zweck (Kein Code)

[image-1]:	assets/IMG_BF47F6534D59-1.jpeg
[image-2]:	assets/Bildschirmfoto%202023-08-07%20um%2008.07.13.png
[image-3]:	assets/Bildschirmfoto%202023-08-07%20um%2008.11.31.png

#learning unit#