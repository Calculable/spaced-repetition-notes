# Hinweis: CoreData Klassen über Änderungen informieren
📣

Das heisst, man kann sie auch explizit über Änderungen informieren, wenn sie es nicht selbst feststellen:

```swift
item.project?.objectWillChange.send()
```

Beachte: Core Data Klassen sind Observable Object


## Zusammenfassung
- wie kann man CoreData Klassen explizit mitteilen, dass sie geändert wurden (und im UI neu gezeichnet werden sollen)


#nur learning unit# #learning unit#