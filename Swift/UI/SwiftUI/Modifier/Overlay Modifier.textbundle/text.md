#  Overlay Modifier
👻
##  Beispiel

```swift
Rectangle()
    .fill(.red)
    .overlay(alignment: .top) {
        Circle()
    }
```

![][image-1]

##  Debugging
- Ein Overlay modifier ist auch häufig sinnvoll für Layout debugging:

```swift
Text("Hello, world")
    .overlay(alignment: .centerFirstTextBaseline) {
        Color.red
            .frame(height: 1)
    }
    .padding(30)
```

![][image-2]
##  Zusammenfassung
- Zweck / Beispiel

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-05-08%20um%2008.16.46.png
[image-2]:	assets/Bildschirmfoto%202024-03-23%20um%2007.32.13.png

#learning unit# #guide