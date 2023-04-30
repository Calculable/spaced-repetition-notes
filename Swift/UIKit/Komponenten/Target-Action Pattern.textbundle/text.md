# Target-Action Pattern
🎯

## Beschreibung des Patterns
- Prinzip: Das Objekt, welches den Event auslöst (zum Beispiel ein Button), enthält alle Informationen um das Event zu verarbeiten. 

## Button aufsetzen
```swift
let button = ReminderDoneButton()
button.addTarget(self, action: #selector(didPressDoneButton(_:)), for: .touchUpInside)
button.id = reminder.id
```

```swift
@objc func didPressDoneButton(_ sender: ReminderDoneButton){
	guard let id = sender.id else { return }
	completeReminder(withId: id)
}
```

## Klasse für den Button
```swift
class ReminderDoneButton: UIButton {
    var id: Reminder.ID?
}
```

## Zusammenfassung
- Was ist das Prinzip des Patterns?
- Wie macht man einen Benutzerdefinierten Button?
- Wie fügt man eine Action zum Button dazu?

#learning unit#