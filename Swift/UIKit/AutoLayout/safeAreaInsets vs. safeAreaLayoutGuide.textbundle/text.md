# safeAreaInsets vs. safeAreaLayoutGuide

## safeAreaInsets

```swift
var safeAreaInsets: UIEdgeInsets { get }
```

> To calculate safe area safeAreaInsets, try to obtain it in viewWIllAppear(),

> safeAreaInsets is a property of UIView that provides the insets that you should use to avoid overlapping with areas such as the status bar, notch, home indicator, or other overlay UI elements that are not part of the usable interface area. These insets are UIEdgeInsets and they provide top, bottom, left, and right values.

## safeAreaLayoutGuide

```swift
var safeAreaLayoutGuide: UILayoutGuide { get }
```

> safeAreaLayoutGuide: safeAreaLayoutGuide is a layout guide provided by UIView that represents the area you should place your content within to avoid being obscured by system UI elements. When you use the safeAreaLayoutGuide, Auto Layout automatically adjusts the constraints when the safe area changes.

## Zusammenfassung
- Was ist der Unterschied?

#learning unit#