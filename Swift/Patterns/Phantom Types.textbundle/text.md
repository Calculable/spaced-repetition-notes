# Phantom Types
👻

## Was ist das?

- Ein Typ der mindestens einer seiner generischen Parameter nicht benötigt

## Beispiel

```swift
struct Employee<Role>: Equatable {
    var name: String
}
```

Für die einzelnen Rollen verwendet man besser "no-case enums" statt structs:

```swift
enum Sales { }
enum Programmer { }
```

## Verwendung

```swift
let zoe1 = Employee<Programmer>(name: "Zoe")
```

## Was bringt das?

- Auch wenn man mit dem Typ nicht arbeitet, kann man Regeln "enforcen", indem man sie als Constraints verwendet (zum Beispiel bei Extensions)


## Zusammenfassung
- Was sind Phantom Types? 
- Wozu braucht man sie?


#nur learning unit#