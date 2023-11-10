
# Swift Data - Delete Rules
🗑️

## Nullify (Default)

Hier wird das `school`-Property der Studenten auf `nil` gesetzt, wenn die Schule gelöscht wird:

```swift
//Innerhalb von School
@Relationship(deleteRule: .nullify, inverse: \Student.school) var students: [Student]
```


## Cascade
Hier werden alle Studenten gelöscht, wenn die Schule gelöscht wird

```swift
//Innerhalb von School
@Relationship(deleteRule: .cascade, inverse: \Student.school) var students: [Student]
```

## Deny

Eine Schule kann erst gelöscht werden, wenn sie keine Studenten hat.

## No Action

Wenn die Schule gelöscht wird, werden die Studenten nicht verändert. Achtung! Das kann dazu führen dass die Studenten eine Schule referenzieren, die es gar nicht mehr gibt!

## Zusammenfassung
- Welche Delete-Rules gibt es? (2 Wichtige)

#learning unit# #Schema