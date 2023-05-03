# 2 UIView initializer
🛫

## `init(frame:)`

- Frame-Origin: Relativ zur Superview
- Oftmals kann man einfach ein beliebiges Frame mitgegeben (default Frame), weil das Frame später sowieso durch die Constraints überschrieben wird.
- Beispiel: `super.init(frame: .zero)`


## `init?(coder:)`

- Wird vom Storyboard oder Nib-Files aufgerufen
- Oftmals wird hier einfach ein `fatalError` geworfen

##  Zusammenfassung
- Wie kann man init(frame: ) implementieren
- Warum braucht man init?(coder:)?

#learning unit#