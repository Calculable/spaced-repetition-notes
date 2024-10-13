# UIKit Layout Margins
🖼️

## Zweck
- Views haben einen Margin:
- Ein Button hat zum Beispiel ein Default-Margin von 8px
![][image-1]

- Zweck: Statt für jede Subview einen Abstand zum Rand zu setzen, können sich die Subviews an den Layout Margins definieren



## Custom Margins
- Jede View kann gewünschte Margins definieren:

```swift
self.view.directionalLayoutMargins = 
	NSDirectionalEdgeInsets(
		top: self.view.directionalLayoutMargins.top,
		leading: 16,
		bottom: self.view.directionalLayoutMargins.bottom,
		trailing: 64
	)
```

## layoutMarginsGuide in Constraints verwenden

Achtung - der LayoutMarginsGuide bezieht sich auf den inneren „Rahmen“ der View, ist also kleiner als die View selbst!

Man kann das für Constraints verwenden

```swift
childView.topAnchor.constraint(equalTo: view.layoutMarginsGuide.topAnchor)
```

Auch in Xcode kann man das auswählen wenn man ein Constraint zwischen Child und Parent erstellt:

![][image-2]



##  Beispiele

### Child (blau) berücksichtigt Layout Margins des Parents (Grün) nicht

![][image-3]

```swift
NSLayoutConstraint.activate([
childView.topAnchor.constraint(equalTo: view.topAnchor),
childView.bottomAnchor.constraint(equalTo: view.bottomAnchor),
childView.leadingAnchor.constraint(equalTo: view.leadingAnchor),
childView.trailingAnchor.constraint(equalTo: view.trailingAnchor)])
```


### Child (blau) berücksichtigt Custom Layout Margins des Parents (Grün):

![][image-4]

```swift
view.directionalLayoutMargins = NSDirectionalEdgeInsets(top: 100, leading: 30, bottom: 30, trailing: 0)
NSLayoutConstraint.activate([
    childView.topAnchor.constraint(equalTo: view.layoutMarginsGuide.topAnchor),
    childView.bottomAnchor.constraint(equalTo: view.layoutMarginsGuide.bottomAnchor),
    childView.leadingAnchor.constraint(equalTo: view.layoutMarginsGuide.leadingAnchor),
    childView.trailingAnchor.constraint(equalTo: view.layoutMarginsGuide.trailingAnchor)])
```

Beachte: Auf der Trailing-Seite wurde das trailing von 0 nicht übernommen, vermutlich weil es kleiner ist als das Minimum


## Missverständnis

- Mit dem Layout Margins sagt man nicht aus, wie viel Abstand andere Elemente zu dieser View haben sollen, es geht um Parent-Child Beziehungen

## Minimum Margins
Hinweis: Wenn die gewählten directionalLayoutMargins das Minimum vom System unterschreiten, wird stattdessen das Minimum berücksichtigt. Man kann das Minimum aber auch anpassen. ()

## Siehe auch

- insetsLayoutMarginsFromSafeArea: [ulysses://x-callback-url/open?id=akFUYtOyGklypW34J4JG7Q][1]
- preservesSuperviewLayoutMargins: [ulysses://x-callback-url/open?id=akFUYtOyGklypW34J4JG7Q][2]

## Zusammenfassung
- Zweck
- Wie kann sich eine Child-View an den Layout Margins des Parents orientieren

[1]:	ulysses://x-callback-url/open?id=akFUYtOyGklypW34J4JG7Q
[2]:	ulysses://x-callback-url/open?id=akFUYtOyGklypW34J4JG7Q

[image-1]:	assets/Bildschirmfoto%202023-07-24%20um%2018.48.53.png
[image-2]:	https://miro.medium.com/v2/resize:fit:1096/format:webp/1*IxU4Xtg8ahAn0KJa_gHcPA.png
[image-3]:	assets/Simulator%20Screenshot%20-%20iPhone%2014%20Pro%20-%202023-07-25%20at%2007.38.54.png
[image-4]:	assets/simulator_screenshot_1D7734FD-666B-4350-B838-C311AE14E7DA.png

#learning unit# #guide