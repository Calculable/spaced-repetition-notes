# Option Set

## Zweck
- Wie Enum, aber man kann mehrere Optionen auf’s Mal auswählen

## Beispiel

```swift
struct UserRoles: OptionSet {
    let rawValue: Int

    static let status = UserRoles(rawValue: 1 << 0)
    static let create = UserRoles(rawValue: 1 << 1)
    static let destroy = UserRoles(rawValue: 1 << 2)
    static let all: UserRoles = [.status, .create, .destroy]
}
```

> Each of those should have a unique raw value, so its common to use bit-shifting to avoid mistakes.

## Warum verwendet man die Bitwise Operatoren?
- Jede Option muss eine eindeutige Zahl haben
- Wenn man mehrere Optionen miteinander kombiniert, wird der OR-Operator angewendet
- So kann man sicher sein, dass auch zusammengesetzte Roles immer eindeutig sind.
- Im Beispiel oben hätte `status` den Wert `1` `create` den Wert `2`, `destroy` den Wert `4` und `all` den Wert `7`

## Options Sets sehen aus wie Arrays

Beachte: Ein Array wird automatisch in das OptionSet konvertiert:

```swift
let roles1: UserRoles = [.create]
let roles2: UserRoles = [.create, .destroy]
let roles3: UserRoles = [.create, .destroy, .status]
let roles4 = UserRoles.all
```


##  Zusammenfassung
- Eigenes Option Set definieren
- Option Set zuweisen

#learning unit#