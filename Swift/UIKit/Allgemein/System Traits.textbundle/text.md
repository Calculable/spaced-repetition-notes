# System Traits
ℹ️

## Traits auslesen

```swift
raitCollection.verticalSizeClass == .Compact
```


##  Wo werden Traits ausgelesen?

###  Heute

- Heute Empfohlen: `viewIsAppearing`
- Das ist, nachdem die View bereits zur Hierarchie hinzugefügt wurde und die trait Collection unf View Geometrie aktuell ist

### Früher

```swift
//im View Controller
//nachdem die Subviews ge-layoutet wuden. Ab diesem Moment jat die View aktualisierte "bounds"
override func viewDidLayoutSubviews() {
	let isCompact = traitCollection.verticalSizeClass == .Compact
	//...
}
```

```swift
//in View
//Das wird immer aufgerufen, wenn sich das Frame ändert (zum Beispiel wechsel von Portrait in Landscape)
override func layoutSubviews() {
	//...
}
```

###  traitCollectionDidChange
- Gibt es sowohl im ViewController als auch in der View
- So wird man informiert, wenn sich die Trait-Collection verändert

```swift
traitCollectionDidChange(previousTraitCollection:)
```

oder wen man es animieren möchte:

```swift
willTransitionToTraitCollection(_:withTransitionCoordinator:)
```



## Welche Traits sind verfügbar?

![][image-1]

(Es gibt auch weitere: userInterfaceIdiom, displayStyle, forceTouchCapability, ...)

(userInterfaceIdiom: Welche "Art" von Gerät ist es?)

## Traits überschreiben
- Das betrifft dann alle Views, ViewControllers etc. unterhalb der aktuellen Hierarchiestufe

## Prüfen, ob sich etwas verändert hat

```swift
if traitCollection.hasDifferentColorAppearance(comparedTo: previousTraitCollection) {
            guard let circlePath = positionView.layer.sublayers?.first as? CAShapeLayer else {
                return
            }
            circlePath.fillColor = SBBColorSemantic.ConnectionPearlsView.positionTint.cgColor
        }
```

## Wer hat Zugriff auf die Traits

![][image-2]

##  Eigene Traits definieren

Mit iOS 17 kann man eigene Traits definieren

![][image-3]


## Verhalten: Wer "erbt" Traits?

Vor iOS 17:

![][image-4]

Mit iOS 17:

![][image-5]

=\> View Controller erben jetzt die Traitcollection von der View's superview

> Because view controllers now inherit their traits from the view hierarchy, a view controller’s view must be in the hierarchy for the view controller to receive updated traits.


##  Zusammenfassung
- Beispiel: In einem View Controller herausfinden, ob man sich in der "Compact" Size Class befindet
- Wo greift man in der Regel auf die Traits zu? (eine Lifecycle-Methode und eine zusätzliche Funktion)

[image-1]:	assets/Bildschirmfoto%202023-10-02%20um%2010.40.28.png
[image-2]:	assets/Bildschirmfoto%202023-10-02%20um%2010.43.03.png
[image-3]:	assets/Bildschirmfoto%202023-10-02%20um%2010.40.49.png
[image-4]:	assets/Bildschirmfoto%202023-10-02%20um%2010.44.54.png
[image-5]:	assets/Bildschirmfoto%202023-10-02%20um%2010.45.36.png

#learning unit#