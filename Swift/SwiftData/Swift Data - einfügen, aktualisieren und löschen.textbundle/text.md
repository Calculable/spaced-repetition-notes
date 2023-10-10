# Swift Data - einfügen, aktualisieren und löschen
✍️

## Einfügen

```swift
var myTrip = Trip(name: "Birthday Trip", destination: "New York")

context.insert(myTrip)
```

## Löschen

###  Einzelnes Objekt
```swift
context.delete(myTrip)
```

### Alle Objekte
Wenn man alle Objekte eines bestimmten Typs löschen möchte:

```swift
try modelContext.delete(model: Trip.self)
```

### Mit Predicate

```swift
try modelContext.delete(model: Trip.self, where: #Predicate { trip in
    trip.locations.isEmpty
})
```

### Hinweis
- Es wird erst beim nächsten Speichern effektiv gelöscht
- Bis dann hat man noch darauf zugriff über `deletedModelsArray`
- Man kann noch ein Rollback machen.
## Aktualisieren

```swift
myTrip.name = "new name"
```

- Man muss nichts speziell beachten, man kann einfach das Model anpassen
- Dank dem `@Model` Macro wird es automatisch gespeichert, man muss nichts mehr weiter beachten
- Achtung - Speichern muss man es trotzdem, das geschieht aber in vielen Fällen automatisch

## Speichern

```swift
 try context.save() //nicht zwingend wenn man SwiftUI verwendet
```


Beachte: In SwiftUI muss man nicht das  Speichern des Kontext denken:

- Swift Data speichert den Model Context automatisch
- Das Speichern wird durch UI-Events und User Input ausgelöst
- Falls nötig, kann man `save` immer noch manuell aufrufen (zum Beispiel bevor man den SwiftData-Speicher auf eine Art exportiert)


## Zusammenfassung
- Objekte erstellen/einfügen
- Objekte löschen
- Objekte aktualisieren
- Kontext speichern + Wann ist das nötig?


#learning unit#