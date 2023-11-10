# Swift Data - einfügen, aktualisieren und löschen
✍️

## Einfügen

```swift
var myTrip = Trip(name: "Birthday Trip", destination: "New York")

context.insert(myTrip)
```

Bei verknüpften Objekten reicht es, ein einzelnes Objekt einzufügen

## Löschen

###  Einzelnes Objekt
```swift
context.delete(myTrip)
```

> First, when you ask your model context to delete an object, it is only marked for deletion. The actual deletion won't take place until the next save is triggered; in the meantime the object will still be around, just stored in the deletedModelsArray of your context. Objects marked for deletion but not yet actually deleted will still appear in results from @Query.
- Man kann es aber mit `model.isDeleted` rausfiltern

> if any part of your app retains a copy of a deleted model, isDeleted will appear true at first, but it may then flip back to false – even though the object itself has been deleted.

> Fourth, as a result of all these there's very little point trying to read the isDeleted in the disabled() SwiftUI view modifier – you might think it's helpful to disable a form if an object no longer exists, but in practice it's just a bit too quirky to rely upon.



### Alle Objekte
Wenn man alle Objekte eines bestimmten Typs löschen möchte:

```swift
try modelContext.delete(model: Trip.self)
```

`deleteAllData()` funktioniert nicht!

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

> In Core Data it was common advice to always check a view context's hasChanges property before trying to save, to avoid unnecessary work.

> In SwiftData this advice is no longer important – just call save() whenever you want, or let autosave do it for you, and you'll be fine, because there's no performance impact.
## Zusammenfassung
- Objekte erstellen/einfügen
- Objekte löschen
- Objekte aktualisieren
- Kontext speichern + Wann ist das nötig?


#learning unit# #Daten