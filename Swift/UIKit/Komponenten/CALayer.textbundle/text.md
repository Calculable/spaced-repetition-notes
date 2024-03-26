# CALayer
🪟

##  Was ist der CALayer einer View 
- Jede View hat ein CALayer
- Kümmert sich um die Visuelle Darstellung der View wie das Rendering
- Man kann auch mehrere Layer kombinieren (zum Beispiel als Maske)
- Eine View kann auch mehrere Layers haben
- MAn kann auf einen Layer mit eine UIBezierPath zeichnen (mit unterschiedlichhen Frames)
- 

## Man kann damit gewisse Attribute von Komponenten anpassen

```swift
imageView.layer.borderColor = UIColor(white: 0, alpha: 0.3).cgColor
imageView.layer.borderWidth = 2
imageView.layer.cornerRadius = 3
myView.layer.shadowColor = UIColor.black.cgColor
myView.layer.shadowOpacity = 0.5
```

Beachte: Man verwendet `cgColors`, weil der `CALayer` eine Abstraktionsschicht tiefer ist.

##  Zusammenfassung
- Wozu ist der CALayer gut? (keine Details)

#learning unit#