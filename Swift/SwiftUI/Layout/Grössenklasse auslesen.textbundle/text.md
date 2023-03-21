# Grössenklasse auslesen
📱

Es gibt nur `compact` und `regular` nichts dazwischen. 

```swift
@Environment(\.horizontalSizeClass) var sizeClass
```


```swift
if sizeClass == .compact {
    //... (jetzt zum Beispiel VStack verwenden weil man Horizontal eingeschränkt ist )
} else {
    //... (jetzt zum Beispiel HStack verwenden)
}
```

![][image-1]

## Zusammenfassung
- Wie list man die Grössenklasse des Gerätes aus?

[image-1]:	assets/Bildschirmfoto%202022-08-24%20um%2015.38.11.png

#learning unit#