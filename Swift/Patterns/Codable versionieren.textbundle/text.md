# Codable versionieren
🕰️

## Problem

- Man möchte beim Server andere Daten zurückgeben -\> Hier muss man dem User ein Popup präsentieren, dass er die App aktualisiert

- Wenn man lokale Daten hat, dann muss man sowohl mit dem alten als auch mit dem neuen Format umgehen können (zum Beispiel wenn ein Nutzer die App aktualisiert, aber noch das alte Datenformat verwendet)

## Variante 1: mit Optionals arbeiten

```swift
struct Employee: Decodable {
    var id: Int
    var name: String
    var age: Int
    var city: String?  //neu dazugekommen
}
```

- **Problem**: Der Code wird "messy"


## Variante 2: Mit verschiedenen Versionen arbeiten

```swift
struct Employee {
    var id: Int
    var name: String
    var age: Int
    var country: String
}
```

- **Beachte**: Hier schreibt man nicht `Decodable`


### Extension: Employee-Versioned.swift

```swift
extension Employee: Decodable {
    private struct EmployeeV1: Decodable {
        let id: Int
        let name: String
        let age: Int
    }

    private struct EmployeeV2: Decodable {
        let id: Int
        let name: String
        let currentAge: Int
        let country: String
    }
}
```

- **Beachte**: das sind alles Konstanten, weil man sie nur kurzfristig benötigt


> Now for the important part: rather than asking Swift to synthesize the `Decodable` support for `Employee` itself, we’re instead going to attempt to decode each of those versioned types by hand, and if any works use its data to create a new instance of our outer struct.

```swift
init(from decoder: Decoder) throws {
    do {
        let employee = try EmployeeV2(from: decoder)
        self.init(id: employee.id, name: employee.name, age: employee.currentAge, country: employee.country)
    } catch {
        let employee = try EmployeeV1(from: decoder)
        self.init(id: employee.id, name: employee.name, age: employee.age, country: "")
    }
}
```

Hier wird für jede Version versucht, ob es sich serialisieren lässt und falls ja, werden die Daten in das Haupt-Struct übertragen.

## Variante 3: Custom Decoder Logic

```swift
extension Employee: Decodable {
    enum CodingKeys: CodingKey {
        case id, name, age, currentAge, country
    }

    init(from decoder: Decoder) throws {
        let container = try decoder.container(keyedBy: CodingKeys.self)

        id = try container.decode(Int.self, forKey: .id)
        name = try container.decode(String.self, forKey: .name)

        if let ageV2 = try container.decodeIfPresent(Int.self, forKey: .currentAge) {
            age = ageV2
        } else {
            age = try container.decode(Int.self, forKey: .age)
        }

        country = try container.decodeIfPresent(String.self, forKey: .country) ?? ""
    }
}
```

- **Nachteile**: Komplexität, es werden auch ungültige Formate akzeptiert (zum Beispiel eine Mischung aus Version 1 und Version 2)


## Zusammenfassung
- Welche drei Varianten gibt es, um Codeable zu versionieren? (nur Konzept, ohne Details)


#nur learning unit#