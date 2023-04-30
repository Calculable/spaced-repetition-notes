# Learning: Intrinsic Content Size für View mit StackView
↕️

## Problem

Eine View, welche eine Content View beinhaltet, hatte keine Intrinsic Content Size mehr

![][image-1]


##  Erklärung

- Eine StackView hat keine Intrinsic Content Size!
- =\> Selbst wenn alle Elemente innerhalb der Stack View eine Intrinsic Content Size besitzen
- Das macht auch Sinn, weil die Stack View kann ja die Elemente je nachdem unterschiedlich „Spacen“, je nachdem, wie viel Platz vorhanden ist

## Lösung

Wenn man trotzdem will, das die StackView eine Intrinsic Content Size hat, verwendet man:

```swift
stackView.systemLayoutSizeFitting(
	UIView.layoutFittingCompressedSize
)
```

Optional auch mit einem weiteren Parameter:

```swift
stackView.systemLayoutSizeFitting(view.frame.size, withHorizontalFittingPriority: .required, verticalFittingPriority: .defaultLow)
```

![][image-2]

## Zusammenfassung
- Was ist die Erklärung und Lösung? (nicht den genauen Methodennamen kennen)

[image-1]:	assets/DraggedImage.png
[image-2]:	assets/DraggedImage-1.png

#learning unit#