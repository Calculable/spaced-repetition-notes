# Learning: Diffable Data Source animiert nicht, obwohl `updateSnapshot` aufgerufen wurde?
🧠
## Problem

Obwohl der folgende Code aufgerufen wurde, hat sich das UI nicht aktualisiert, wenn man auf den `done` Button geklickt hat:

```swift
func updateSnapshot() {
	var snapshot = Snapshot()
	snapshot.appendSections([0])
	snapshot.appendItems(reminders.map { $0.id })
	dataSource.apply(snapshot)
}
```

![][image-1]

## Ursache

Die Diffable Datasource generiert das Diff nur anhand der übergebenen ID’s. Und diese verändern sich ja nicht, nur weil sich der Done-Status ändert.

## Lösung

```swift
func updateSnapshot(reloading ids: [Reminder.ID] = []) {
	var snapshot = Snapshot()
	snapshot.appendSections([0])
	snapshot.appendItems(reminders.map { $0.id })
     if !ids.isEmpty {
		snapshot.reloadItems(ids)
	}
	dataSource.apply(snapshot)
}
```

## Zusammenfassung
- Problem
- Ursache
- Lösung

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-04-24%20um%2008.10.39.png

#learning unit#