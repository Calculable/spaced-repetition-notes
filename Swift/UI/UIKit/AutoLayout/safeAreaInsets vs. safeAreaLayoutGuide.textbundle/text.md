# safeAreaInsets vs. safeAreaLayoutGuide


## safeAreaLayoutGuide

=\> Idr. arbeitet man damit, wenn man AutoLayout verwendet...

```swift
view.safeAreaLayoutGuide
```

> safeAreaLayoutGuide: safeAreaLayoutGuide is a layout guide provided by UIView that represents the area you should place your content within to avoid being obscured by system UI elements. When you use the safeAreaLayoutGuide, Auto Layout automatically adjusts the constraints when the safe area changes.

Daran kann man sich beim Layouten orientieren...


```swift
NSLayoutConstraint.activate([
    blue.topAnchor.constraint(equalTo: green.safeAreaLayoutGuide.topAnchor),
    blue.bottomAnchor.constraint(equalTo: green.safeAreaLayoutGuide.bottomAnchor),
    blue.leadingAnchor.constraint(equalTo: green.safeAreaLayoutGuide.leadingAnchor),
    blue.trailingAnchor.constraint(equalTo: green.safeAreaLayoutGuide.trailingAnchor)])
```
 

## safeAreaInsets

```swift
view.safeAreaInsets
```

- "Einfach nur 4 Zahlen"
- Liest man idr. im viewWillAppear aus

> safeAreaInsets is a property of UIView that provides the insets that you should use to avoid overlapping with areas such as the status bar, notch, home indicator, or other overlay UI elements that are not part of the usable interface area. These insets are UIEdgeInsets and they provide top, bottom, left, and right values.


## Zusammenfassung
- Was ist der Unterschied?

#learning unit# #guide