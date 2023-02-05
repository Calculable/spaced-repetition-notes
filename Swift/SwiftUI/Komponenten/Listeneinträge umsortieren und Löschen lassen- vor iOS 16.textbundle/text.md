# Listeneinträge umsortieren und Löschen lassen: vor iOS 16 👆


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

- Das gleiche geht auch für `onDelete`


## Quelle

[How to let users move rows in a list - a free SwiftUI by Example tutorial (hackingwithswift.com)][1]

## Zusammenfassung
- Wie kann man im Code darauf reagieren oder Versionen vor iOS 16 unterstützen? (nur Konzept, nicht genauen Code)

[1]:	https://www.hackingwithswift.com/quick-start/swiftui/how-to-let-users-move-rows-in-a-list

#nur learning unit#