# Accessibility: Reihenfolge der Accessibility Elements
🦮 

##  Standartverhalten
- Elemente werden standartmässig von Links nach Rechts und dann von Oben nach Unten vorgelesen

##  UIKit

### Reihenfolge explizit festlegen

```swift
myView.accessibilityElements = [firstLabel, secondLabel, thirdLabel, forthLabel]
```
![][image-1]
### Elemente Gruppieren

Oft reicht es, wenn man die Elemente gruppiert, denn Standartmässig liest Voice Over von Links nach Rechts und dann von oben nach unten.

```swift
blueContainer.isAccessibilityElement = false //(default)
blueContainer.shouldGroupAccessibilityChildren = true

redContainer.isAccessibilityElement = false //(default)
redContainer.shouldGroupAccessibilityChildren = true
```


Beispiel: Ohne  `shouldGroupAccessibilityChildren = true` (Gif)
![][image-2]
Beispiel: Mit `shouldGroupAccessibilityChildren = true` (Gif)
![][image-3]

## SwiftUI

```swift
// The highest priority is read first
View()
  .accessibilitySortPriority(2)
View()
  .accessibilitySortPriority(1)
View()
  .accessibilitySortPriority(3)
```

##  Zusammenfassung
- SwiftUI und UIKit: Reihenfolge der Accessibility-Elemente festlegen

[image-1]:	assets/RPReplay_Final1707058705.gif
[image-2]:	assets/RPReplay_Final1707058841.gif
[image-3]:	assets/RPReplay_Final1707058705-1.gif

#learning unit#