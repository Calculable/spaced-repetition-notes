# Mask Modifier
🎭
## Ohne Mask

```swift
Rectangle()
    .fill(.red)
}
```

![][image-1]

## Mit Mask

```swift
Rectangle()
    .fill(.red)
    .mask(alignment: .top) {
        Circle()
    }
}
```

![][image-2]


## Unterschied Mask und Clip Shape
- Der Mask Modifier zeigt nur diejenigen Inhalte der View an, die auf der Maske liegen.
- Die Maske kann zum Beispiel auch ein Text sein oder „Löcher“ beinhalten
- Clip Shape hingegen verändert nur die äussere Form der View


##  Zusammenfassung
- Zweck / Beispiel
- Unterschied zum ClipShape Modifier

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-05-08%20um%2008.18.08.png
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-05-08%20um%2008.18.30.png

#learning unit# #guide