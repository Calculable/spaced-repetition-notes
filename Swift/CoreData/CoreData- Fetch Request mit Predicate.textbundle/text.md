# CoreData: Fetch Request mit Predicate
🐶

## Beispiel
```swift
@FetchRequest(sortDescriptors: [], predicate: NSPredicate(format: "universe == 'Star Wars'")) var ships: FetchedResults<Ship>
```

## Mit Platzhalter
```swift
NSPredicate(format: "universe == %@", "Star Wars"))
```

## Siehe auch
- CoreData: Fetch Request mit Sort Descriptor
- Man kann FetchRequests auch ohne Annotation erstellen (also im Code) - siehe Zusammenfassung

## Zusammenfassung
- Mit und ohne Platzhalter