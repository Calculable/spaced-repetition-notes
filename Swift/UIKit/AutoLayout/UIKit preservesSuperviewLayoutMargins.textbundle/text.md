# UIKit preservesSuperviewLayoutMargins
🖼️

## Zweck

- Definiert, ob die Layout Margins eines Parents auch einen Einfluss auf die Kinder haben sollen, wenn sich die Kinder selbst innerhalb der Margins des Parents befinden (also die LayoutMargins der Kinder vergrössern können)

- Standartmässig ist dieses Property `false`

![][image-1]

##  Beispiel
Beispiel: Man hat 3 Views:
- Grün
	- Blau
		- Rot

Die Grüne View ist die Root view. Sie hat layoutMargins:

```swift
green.directionalLayoutMargins = NSDirectionalEdgeInsets(top: 100, leading: 30, bottom: 30, trailing: 0)
```

Die Blaue View hat keine Layout Margins und nimmt die Grösse der gesamten Grünen View ein, ohne Layout Margins zu berücksichtigen:

```swift
NSLayoutConstraint.activate([
    blue.topAnchor.constraint(equalTo: green.topAnchor),
    blue.bottomAnchor.constraint(equalTo: green.bottomAnchor),
    blue.leadingAnchor.constraint(equalTo: green.leadingAnchor),
    blue.trailingAnchor.constraint(equalTo: green.trailingAnchor)])
```

Die Rote View orientiert sich an den layout margins der blauen View und somit automatisch auch Safe Area:

```swift
NSLayoutConstraint.activate([
    red.topAnchor.constraint(equalTo: blue.layoutMarginsGuide.topAnchor),
    red.bottomAnchor.constraint(equalTo: blue.layoutMarginsGuide.bottomAnchor),
    red.leadingAnchor.constraint(equalTo: blue.layoutMarginsGuide.leadingAnchor),
    red.trailingAnchor.constraint(equalTo: blue.layoutMarginsGuide.trailingAnchor)])
```

![][image-2]

Wenn man jetzt aber schreibt `blue.preservesSuperviewLayoutMargins = true`, dann werden die Layout Margins der blauen View so angepasst, dass auch die ursprünglichen Layout Margins der Grünen View berücksichtigt werden:

![][image-3]

[image-1]:	assets/DraggedImage.tiff
[image-2]:	assets/simulator_screenshot_E0F94B8B-9894-4056-B05C-29F1772B631D.png
[image-3]:	assets/Simulator%20Screenshot%20-%20iPhone%2014%20Pro%20-%202023-07-25%20at%2008.11.17.png

#learning unit#