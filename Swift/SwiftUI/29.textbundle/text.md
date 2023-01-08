# CoreData: Grundkonzepte 📟
::29::

##  Grund-Konzepte
- Managed Objects sind Hashable und Identifiable
- Das Konzept von Optional ist anders
- Core Data ist „Lazy“
- Fetch-Request sind ein anderes Kapitel

## Save

```swift
@Environment(\.managedObjectContext) var moc
```

```swift
let student = Student(context: moc)
student.id = UUID()
student.name = "\(chosenFirstName) \(chosenLastName)"
```

```swift
try moc.save()
```

```swift
if moc.hasChanges {
    try moc.save()
}
```

## Delete

```swift
moc.delete(book)
//kontext speichern
```

## Zusammenfassung
- Protokolle von Managed Objects
- Save
- Delete 