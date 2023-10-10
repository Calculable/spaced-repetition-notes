# System Traits
ℹ️

## Traits auslesen

In diesem Beispiel wurde der Code innerhalb von `viewDidLayoutSubivews` ausgeführt.

```swift
//im View Controller
override func viewDidLayoutSubviews() {
	let isCompact = traitCollection.verticalSizeClass == .Compact
	//...
}
```

```swift
//in View
override func layoutSubviews() {
	//...
}
```

(layoutSubviews and viewDidLayoutSubviews) are the best places to use traits


## Welche Traits sind verfügbar?

![][image-1]

(Es gibt auch weitere: userInterfaceIdiom, displayStyle, forceTouchCapability, ...)

(userInterfaceIdiom: Welche "Art" von Gerät ist es?)

## Traits überschreiben
- Das betrifft dann alle Views, ViewControllers etc. unterhalb der aktuellen Hierarchiestufe

## traitCollectionDidChange

Darüber wird man informiert, wen sich die Trait Collection Verändert:

```swift
traitCollectionDidChange(previousTraitCollection:)
```

oder wen man es animieren möchte:

```swift
willTransitionToTraitCollection(_:withTransitionCoordinator:)
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
- In welcher Callback-Methode greift man normalerweise auf die Traits zu?

[image-1]:	assets/Bildschirmfoto%202023-10-02%20um%2010.40.28.png
[image-2]:	assets/Bildschirmfoto%202023-10-02%20um%2010.43.03.png
[image-3]:	assets/Bildschirmfoto%202023-10-02%20um%2010.40.49.png
[image-4]:	assets/Bildschirmfoto%202023-10-02%20um%2010.44.54.png
[image-5]:	assets/Bildschirmfoto%202023-10-02%20um%2010.45.36.png

#learning unit#