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

##  Zusammenfassung
- Zweck / Beispiel

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-05-08%20um%2008.18.08.png
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-05-08%20um%2008.18.30.png

#learning unit#