# Aus einem Array löschen
❌

## Problem
- Bei der `onDelete`-Methode bekommt man ja mehrere Indexe, die man aus dem Array entfernen soll
- Dazu sollte man sich Gedanken machen, weil sich durch die einzelnen Löschvorgänge ja wiederum die Indexe ändern können. 

## IndexSet

> We’re passed an  `IndexSet`, not an array, and this is a special albeit rarely used collection type that is  _already sorted_

## Lösungsansatz: Core Data

Wenn man mit Core-Data arbeitet, kann man einfach diesen Code verwenden:

```swift
.onDelete { offsets in
    let allItems = project.projectItems //optional, zum Beispiel wenn projectItems ein Computed Property ist und man es nicht jedes mal berechnen möchte

    for offset in offsets {
        let item = allItems[offset]
        dataController.delete(item)
    }

    dataController.save()
}
```

> When you delete a Core Data object, it doesn’t fully go away straight away – you can “delete” a whole bunch of objects in one pass, and nothing actually changes. This means our array indexing won’t change as each item is deleted, no matter what order objects are deleted in.

## Lösungsansatz: direkt löschen

Es gibt für Arrays auch bereits eine fertige Methode, der man ein `IndexSet` übergeben kann, um Elemente zu löschen, so muss man nicht selbst durch das `IndexSet` iterieren


## Zusammenfassung
- Zu welchen Problemen kann es kommen, wenn man mehrere Elemente aus einem Array entfernen will?
- Inwiefern macht `IndexSet` diese Aufgabe einfacher?
- Wie kann man das Problem mit CoreData lösen?
- Wie kann man das Problem ohne CoreData lösen?


#learning unit#