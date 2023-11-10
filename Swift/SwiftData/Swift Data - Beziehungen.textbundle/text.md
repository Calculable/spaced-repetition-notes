
# Swift Data - Beziehungen
🖇️
## Bidirektionale One-to-Many Beziehung

### Beispiel: Implizit

Das reicht bereits aus:

```swift
@Model
class School {
    var name: String
    var students: [Student]

    init(name: String, students: [Student]) {
        self.name = name
        self.students = students
    }
}

@Model
class Student {
    var name: String
    var school: School? //Optional

    init(name: String, school: School) {
        self.name = name
        self.school = school
    }
}
```

- Beachte, es braucht kein `@Relationship` Attribut
- Beachte: Die `school` im Student muss Optioal sein!

###  Beispiel: Explizit

**Wichtiger Hinweis**: Man darf nur an einer Stelle ein @Relationship-Makro haben! [https://www.hackingwithswift.com/quick-start/swiftdata/common-swiftdata-errors-and-their-solutions][1] Ansonsten Error (“Circular reference resolving attached macro 'Relationship’.”)


**Variante 1: @Relationship In School:**

```swift
@Relationship(deleteRule: .cascade, inverse: \Student.school) var students: [Student]
```
(default delete rule: `nullify`)

**Variante 2: @Relationship in Student**
```swift
@Relationship(inverse: \School.students) var school: School
```


## Swift Data - One-to-One Beziehung

- Die Attribute auf beiden Seiten müssen Optional sein

```swift
@Model
class Country {
    var capitalCity: City? //Optional
	//...
}
	
@Model
class City {
    var country: Country? //Optional
	//...
}
```

- So wird es dann gespeichert:

```swift
let country = Country(name: "England")
let city = City(name: "London", latitude: 51.507222, longitude: -0.1275, country: country)

modelContext.insert(city)
```

- Beachte: Man insterted nur eines der beiden Objekte (sonst würde es einen Fehelr geben)

## Swift Data - Many-to-Many Beziehung

- Hier braucht es zwingend ein `@Relationsip`-Attribut (auf einer Seite)

Beispiel:

**Im Actor:**
```swift
var movies: [Movie]
```

**Im Movie:**
```swift
@Relationship(inverse: \Actor.movies) var cast: [Actor]
```

Hinweis: Wenn man einen Actor speichert der einen Film enthält, dann muss man den Film nicht mehr explizit speichern.

> For example, if you attempt to manipulate the movies property of an actor before inserting them, you’ll get a hard crash

(Es ist aber erlaubt, den Initializer aufzurufen)

> You’ll also get a crash with the message “illegal attempt to establish a relationship” if you attempt to insert things out of sequence, like this:

```swift
let mi2 = Movie(name: "Mission: Impossible 2", releaseYear: 2000, cast: [])
modelContext.insert(mi2)

let cruise = Actor(name: "Tom Cruise", movies: [mi2])
let newton = Actor(name: "Thandiwe Newton", movies: [mi2])

modelContext.insert(cruise)
modelContext.insert(newton)
```
![][image-1]

Quelle: [https://www.hackingwithswift.com/quick-start/swiftdata/how-to-create-many-to-many-relationships][2]

## Zusammenfassung
- Wo hat man das @Relationship-Attribut bei Zweiseitigen Beziehungen
- Was ist der Fehler, wenn eine School ein Property `var students: [Student]` hat und der Student ein Property `var school: School`?
- Muss man beim `insert` für beide Objekte aufrufen?

[1]:	https://www.hackingwithswift.com/quick-start/swiftdata/common-swiftdata-errors-and-their-solutions
[2]:	https://www.hackingwithswift.com/quick-start/swiftdata/how-to-create-many-to-many-relationships

[image-1]:	assets/Bildschirmfoto%202023-10-09%20um%2017.10.07.png

#learning unit# #Schema