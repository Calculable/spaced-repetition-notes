# CoreData: Neue Entity erzeugen
📟


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

## Zusammenfassung