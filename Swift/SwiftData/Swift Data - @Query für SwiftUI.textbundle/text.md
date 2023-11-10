# Swift Data - @Query für SwiftUI
🔎

```swift
//Ohne Sortierung
@Query var trips: [Trips]

//Mit Sortierung
@Query(sort: \Trip.startDate, order: .reverse) var trips: [Trip]

//Mit Sort Descriptor
@Query(sort: [SortDescriptor(\Trip.startDate, order: .reverse), SortDescriptor(\Trip.priority)]) var trips: [Trip]

//Mit natürlicher Sortierung (Finder-Style sorting): Test 1, Test 2, Test 3, Test 11 statt Test 1, Test 11, Test 2, Test 3
@Query(sort: [SortDescriptor(\User.name, comparator: .localizedStandard)]) var users: [User]


```


## Zusammenfassung
- Code: Ein Array von Trips, sortiert mit startDate, in umgekehrter Reihenfolge
- Was ist natürliche Sortierung?

#learning unit# #Daten