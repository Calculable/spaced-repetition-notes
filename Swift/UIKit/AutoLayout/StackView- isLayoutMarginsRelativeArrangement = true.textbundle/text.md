# StackView: isLayoutMarginsRelativeArrangement = true
 🥞
- Standartmässig auf "false"
- Wenn es auf True gesetzt ist, dann werden die layoutMargins des StackView von den "arranged Subviews" beachtet.
- Ansonsten werden die layoutMargins einfach ignoriert


```swift
myStackView.layoutMargins = UIEdgeInsets(top: 30, left: 30, bottom: 30, right: 30)
myStackView.isLayoutMarginsRelativeArrangement = true //there will be a 30-point padding around the entire content of the stack view.

```

## Beispiel: 

### Standartverhalten
![][image-1]
### LayoutMarginsRelativeAgrrangement

```swift
myStackView.isLayoutMarginsRelativeArrangement = true 
```

![][image-2]

##  Zusammenfassung
- Was macht dieses Property?

[image-1]:	assets/Simulator%20Screenshot%20-%20iPhone%2015%20Pro%20-%202024-03-21%20at%2019.03.03.png
[image-2]:	assets/simulator_screenshot_199197F9-936B-4707-BF6E-CBE1B4E7016F.png

#learning unit#