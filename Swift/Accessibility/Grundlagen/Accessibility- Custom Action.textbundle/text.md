# Accessibility: Custom Action
🦮

## Infos
- Für viele System-Komponenten wie Buttons ist die Default-Action bereits definiert
- Voice-Over User können durch Swipen nach oben zwischen die Aktionen wechseln:

![][image-1]

Die Action kann man dann im Accessibility Inspector wieder auslesen:

![][image-2]

## UIKit
```swift
cell.accessibilityCustomActions = [doneButtonAccessibilityAction(for: reminder)]
```

```swift
private func doneButtonAccessibilityAction(for reminder: Reminder) -> UIAccessibilityCustomAction
{
    let name = NSLocalizedString(
        "Toggle completion", comment: "Reminder done button accessibility label")
    let action = UIAccessibilityCustomAction(name: name) { [weak self] action in
        self?.completeReminder(withId: reminder.id)
        return true
    }
    return action
}
```

Alternativ kann man es auch so überschreiben

![][image-3]


Quelle: [https://a11y-guidelines.orange.com][1]

Mit iOS 14 kann man eigene Symbole für die Custom Actions anzeigen:

![][image-4]

## SwiftUI

![][image-5]

```swift
.accessibilityAction(named: Text("Select")) {
  // Handle Select
}
.accessibilityAction(named: Text("Edit")) {
  // Handle Edit
}
.accessibilityAction(named: Text("Delete")) {
  // Handle Delete
} 
```

## Zusammenfassung
- Wie kann man bei Voice Over als Nutzer:in eine Custom Action auswählen?

[1]:	https://a11y-guidelines.orange.com

[image-1]:	assets/Bildschirmfoto%202024-01-28%20um%2007.56.15.png
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-04-24%20um%2008.45.48.png
[image-3]:	assets/Bildschirmfoto%202024-02-02%20um%2008.23.03.png
[image-4]:	https://a11y-guidelines.orange.com/en/mobile/images/iOSdev/wwdc20-019-OverviewCustomActions.png
[image-5]:	assets/Bildschirmfoto%202024-01-31%20um%2007.05.35.jpeg

#learning unit#