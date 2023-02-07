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

## Zusammenfassung
- Mit und ohne Platzhalter