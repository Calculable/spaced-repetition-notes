# Matched Geometry Effects
🎲 

##  Beispiel
- Das funktioniert ähnlich wie der „Zauber-Übergang“ in Keynote:


![][image-1]

## Code

```swift
@Namespace var namespace
@State var show = false

var body: some View {
    ZStack {
        if !show {
            Circle()
                .matchedGeometryEffect(id: "shape", in: namespace)
                .frame(width: 100, height: 100)
        } else {
            Circle()
                .matchedGeometryEffect(id: "shape", in: namespace)
                .frame(maxWidth: .infinity, maxHeight: 300)
                .foregroundColor(.yellow) //neu: foregroundStyle
        }
    }
    .onTapGesture {
        withAnimation {
            show.toggle()
        }
    }
}
```

=\> Beachte: Man muss den gleichen namespace verwenden
=\> Man sollte es nicht auf Container anwenden sondern vor allem auf Shapes, Texte und Buttons


## Einen Namespace weitergeben

### Typ des Namepace

```swift
var namespace: Namespace.ID
```

### Beispiel

```swift
MyCustomRow(namespace: namespace)
```

##  Zusammenfassung
- Wozu ist das gut? (Nur Konzept, kein Code)

[image-1]:	assets/2023-03-30%2008.45.31.gif

#learning unit#