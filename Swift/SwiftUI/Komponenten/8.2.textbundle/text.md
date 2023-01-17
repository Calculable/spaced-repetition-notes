# Listeneinträge umsortieren und Löschen lassen 👆

- Mit iOS 16 einfacher dank editActions


## Lösung für iOS 16

```swift
List($users, id: \.self, editActions: .move) { $user in
	Text(user)
}
```

So wird das Array automatisch bearbeitet.

> If you want to add swipe to delete as well, use `.all` rather than just `.move`.

Beachte: Statt List und ForEach zu schachteln hat bereits List die benötigte Funktionalität.

## Lösung vor iOS 16 oder auf move/delete-Event reagieren

```swift
List {
	ForEach(users, id: \.self) { user in
		Text(user)
	}
	.onMove(perform: move) //bzw. onDelete
}
.toolbar {
	EditButton()
}
```

```swift
func move(from source: IndexSet, to destination: Int) {
	users.move(fromOffsets: source, toOffset: destination)
	// bzw. users.remove(atOffsets: offsets)
}
```

## Quelle

[How to let users move rows in a list - a free SwiftUI by Example tutorial (hackingwithswift.com)][1]

## Zusammenfassung
- Wie kann ein Nutzer eine Liste umsortieren / löschen mit iOS 16
- Wie kann man im Code darauf reagieren oder Versionen vor iOS 16 unterstützen? (nur Konzept, nicht genauen Code)

[1]:	https://www.hackingwithswift.com/quick-start/swiftui/how-to-let-users-move-rows-in-a-list

#nur learning unit#