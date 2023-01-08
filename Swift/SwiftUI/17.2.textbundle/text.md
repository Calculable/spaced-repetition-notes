# Grössenklasse auslesen 📱
::17.2::

##  Grössenklasse auslesen

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

## Zusammenfassung
- Wie list man die Grössenklasse des Gerätes aus?