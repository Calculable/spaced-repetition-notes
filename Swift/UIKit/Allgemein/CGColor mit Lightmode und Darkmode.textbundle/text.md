# CGColor mit Lightmode und Darkmode
🌈

CGColor reagiert nicht wie UIColor automatisch auf Lightmode und Darkmode. Deshalb muss man jedes mal wenn der Mode gewechselt wird die entsprechenden Properties erneut setzen:

```swift
class MyView: UIView {
	init() {
		super.init(frame: .zero)
		layer.borderColor = myUIColor.cgColor
	}

    override func traitCollectionDidChange(_ previousTraitCollection: UITraitCollection?) {
    	super.traitCollectionDidChange(previousTraitCollection)
        if traitCollection.hasDifferentColorAppearance(comparedTo: previousTraitCollection) {
            layer.borderColor = myUIColor.cgColor
        }
    }
}
```

##  Zusammenfassung
- Was gibt es zu beachten

#learning unit#