# Accessibility Value
🦮 

![][image-1]

```swift
cell.accessibilityValue =
	reminder.isComplete
		? NSLocalizedString("Completed", comment: "Reminder completed value")
		: NSLocalizedString("Not completed", comment: "Reminder not completed value")
```

Im Accessibility Inspector kann man das Label wieder auslesen:

![][image-2]

## Zusammenfassung
- UIKit: Wie wird ein Accessibility Value definiert?

[image-1]:	https://docs-assets.developer.apple.com/published/ab0d7c596b1efc6bbe38fcfaa815b836/UIK095_004@2x.png
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-04-24%20um%2008.42.51.png

#learning unit#