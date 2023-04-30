# Einen View Controller innerhalb eines anderen View Controllers verwenden
🪆

Innerhalb eines View Controllers: 
```swift
//1. In die View Hierarchie hinzufügen
addChild(anotherViewController)

//2. View hinzufügen
view.addSubview(anotherViewController.view)

//3. View positionieren
anotherViewController.view.leadingAchor = ... //etc.

//4. Did Move
anotherViewController.didMove(toParent: self)
```

##  Zusammenfassung
- Welche 4 Schritte werden benötigt?

#learning unit#