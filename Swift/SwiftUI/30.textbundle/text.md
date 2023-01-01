# CoreData: Fetch Request 🐶
::30::

##  Sort Descriptor

```swift
@FetchRequest(sortDescriptors: [
    SortDescriptor(\.title, order: .reverse),
	SortDescriptor(\.author)
]) var books: FetchedResults<Book>
```

##  Filtering with NSPredicate

### Beispiel
```swift
@FetchRequest(sortDescriptors: [], predicate: NSPredicate(format: "universe == 'Star Wars'")) var ships: FetchedResults<Ship>
```

### Mit Platzhalter
```swift
NSPredicate(format: "universe == %@", "Star Wars"))
```

## Zusammenfassung
- Wie macht man einen Fetch Request (mit Sortierung und Filterung)?