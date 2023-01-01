# Layout 🟪
::17::

## Three Steps

- A parent view proposes a size for its child.
- Based on that information, the child then chooses its own size and the parent must respect that choice.
- The parent then positions the child in its coordinate space.

##  Layout Neutral

Elemente sind Layout-Neutral, wenn sie ihre Childs fragen, wie gross sie sein sollen. Wenn es keine Child-Views gibt nehmen diese Views einfach den vorgeschlagenen Platz des Parents ein (zum Beispiel Color)


##  Relative Positionierung

- Mit Offset-Modifier

```java
Text("Hello, world!")
    .offset(x: 100, y: 100)
```

## Absolute Positionierung

- Mit Position-Modifier

```java
Text("Hello, world!")
    .position(x: 100, y: 100)
```

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
- Nach welchen 3 Regeln werden die UI’s aufgebaut?
- Was bedeutet Layout-Neutral?
- Wie positioniert man eine View Absolut?
- Wie positioniert man eine View relativ?
- Was ist eine Auswirkung, wenn man es absolut positioniert?
- Wie list man die Grössenklasse des Gerätes aus?