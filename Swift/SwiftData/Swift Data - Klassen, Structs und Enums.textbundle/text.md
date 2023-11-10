# Swift Data - Klassen, Structs und Enums

## Hinweis

In meinem Test hat das untere Beispiel nicht funktioniert, und ich musste es so speichern:

```swift
@Transient var parameterType: ParameterType {
    get { ParameterType(rawValue: _parameterType)! }
    set { _parameterType = newValue.rawValue }
}

var _parameterType: ParameterType.RawValue
```

## Beispiel
- Swift Data Models müssen Klassen sein
- Sie dürfen aber Structs und Enums enthalten (wenn diese zu `Codable` konform sind)

```swift
@Model
class Customer {
    var name: String
    var address: Address
	var status: Status

	//Initializer
}

struct Address: Codable {
    var line1: String
    var line2: String
    var city: String
    var postCode: String
}

enum Status: Codable {
    case active
	case inactive(reason: String)
}
```

## Wie wird es gespeichert?
- Die Struct / Enum-Werte werden direkt in der `Customer`-Tabelle abgelegt, es gibt keine eigene Tabelle

## Was kann ein Problem sein?
- Wenn man ein Value-Typ als Array speichert (z.B `[String]` oder `[Address]`) dann wird es als Binary Property abgelegt. Deshalb kann es nicht mehr in Query-Predicates verwendet werden

## Zusammenfassung
- Wie verwendet man Swift Data gemeinsam mit Enum oder Structs
- Was gibt es zu beachten?

#learning unit# #Schema