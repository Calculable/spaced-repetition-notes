# CoreData: Fetch Request mit Sort Descriptor
🐶

##  Beispiel

```swift
@FetchRequest(sortDescriptors: [
    SortDescriptor(\.title, order: .reverse),
	SortDescriptor(\.author)
]) var books: FetchedResults<Book>
```

##  Siehe auch

- Fetch Request mit Predicate
- Man kann FetchRequests auch ohne Annotation erstellen (also im Code) - siehe Zusammenfassung

## Zusammenfassung
- Wie macht man einen Fetch Request (mit Sortierung)?

#learning unit#