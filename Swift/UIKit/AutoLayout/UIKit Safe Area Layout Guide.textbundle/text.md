# UIKit Safe Area Layout Guide
🖼️

```swift
view.safeAreaLayoutGuide //wenn man mit Autolayout arbeitet
view.safeAreaInsets //wenn man nicht mit Autolayout arbeitet
```

### 3

```swift
NSLayoutConstraint.activate([
    blue.topAnchor.constraint(equalTo: green.safeAreaLayoutGuide.topAnchor),
    blue.bottomAnchor.constraint(equalTo: green.safeAreaLayoutGuide.bottomAnchor),
    blue.leadingAnchor.constraint(equalTo: green.safeAreaLayoutGuide.leadingAnchor),
    blue.trailingAnchor.constraint(equalTo: green.safeAreaLayoutGuide.trailingAnchor)])
```

![][image-1]


##  Zusammenfassung
- Auf den Layout Guide zugreifen

[image-1]:	assets/simulator_screenshot_831BA9A2-99C4-4AF5-8D14-4A62E8056638.png

#learning unit#