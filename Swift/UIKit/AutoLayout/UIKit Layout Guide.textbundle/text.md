# UIKit Layout Guide
🖼️

## Zweck
- Ein Layout Guide definiert eine rechteckige Fläche in einer View
- Früher hat man mit Placeholder Views gearbeitet. Das ist jedoch unperformant + kann zu Problemen führen wenn man zum Beispiel Eingabegesten erkennen möchte

## Layout Guide erstellen

```swift
let myLayoutGuide = UILayoutGuide()
view.addLayoutGuide(myLayoutGuide)
```

##  Layout Guide verwenden

Können wie eine View mit Autolayout ausgerichtet werden und andere Elemente können sich daran orientieren

```swift
myLayoutGuide.widthAnchor
	.constraintEqualToAnchor(myView.widthAnchor).active = true
```

## Zusammenfassung
- Zweck
- Layout guide erstellen

## Quelle
[https://developer.apple.com/documentation/uikit/uilayoutguide][1]

[1]:	https://developer.apple.com/documentation/uikit/uilayoutguide

#learning unit#