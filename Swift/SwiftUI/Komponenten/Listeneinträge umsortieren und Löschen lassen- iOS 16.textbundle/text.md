# Listeneinträge umsortieren und Löschen lassen: iOS 16
👆

## Beispiel
Mit iOS 16 einfacher dank editActions

```swift
List($users, id: \.self, editActions: .move) { $user in
	Text(user)
}
```

So wird das Array automatisch bearbeitet.

> If you want to add swipe to delete as well, use `.all` rather than just `.move`.

Beachte: Statt List und ForEach zu schachteln hat bereits List die benötigte Funktionalität.


## Quelle

[How to let users move rows in a list - a free SwiftUI by Example tutorial (hackingwithswift.com)][1]

## Zusammenfassung
- Wie kann ein Nutzer eine Liste umsortieren / löschen mit iOS 16

[1]:	https://www.hackingwithswift.com/quick-start/swiftui/how-to-let-users-move-rows-in-a-list

#nur learning unit# #learning unit#