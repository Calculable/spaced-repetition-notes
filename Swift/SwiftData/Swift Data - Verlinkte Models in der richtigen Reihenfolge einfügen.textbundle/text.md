# Swift Data - Verlinkte Models in der richtigen Reihenfolge einfügen
⤵️
##  Falsch

```swift
let mi2 = Movie(name: "Mission: Impossible 2", releaseYear: 2000, cast: [])
modelContext.insert(mi2)

let cruise = Actor(name: "Tom Cruise", movies: [mi2])
modelContext.insert(cruise)
```

Hier ist das Problem dass zu einem Zeitpunkt ein Objekt existiert dass in der Datenbank existiert während das andere Objekt nicht in der Datenbank existiert

##  Richtig

```swift
let mi2 = Movie(name: "Mission: Impossible 2", releaseYear: 2000, cast: [])

let cruise = Actor(name: "Tom Cruise", movies: [mi2])
modelContext.insert(cruise)
```

## Zusammenfassung
- Wie fügt man zwei verlinkte Objekte in der Datenbank ein? (Movie mit einem Array an Actors)

#Daten #learning unit#