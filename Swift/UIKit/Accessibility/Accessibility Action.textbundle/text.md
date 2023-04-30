# Accessibility Action
🦮

> System controls have default actions, but you can also add custom actions. For example, swipe actions like deleting a row are represented in VoiceOver as custom actions

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

Die Action kann man dann im Accessibility Inspector wieder auslesen:

![][image-1]

## Zusammenfassung
- UIKit: Wie wird eine Accessibility Action definiert? (Konzept)

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-04-24%20um%2008.45.48.png

#learning unit#