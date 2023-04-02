# Views absolut positionieren
🖼️

Achtung: Hier darf man `translatesAutoresizingMaskIntoConstraints = false` NICHT setzen!

```swift
let frame = CGRect(x: 40, y: 50, width: 60, height: 70)
letterButton.frame = frame
buttonsView.addSubview(letterButton)
```

## Zusammenfassung
- Wie positioniert man eine View absolut in UIKit?
- Welche Option darf nicht gesetzt werden?

#learning unit#