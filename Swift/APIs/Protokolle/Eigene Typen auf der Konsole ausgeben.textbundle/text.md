# Eigene Typen auf der Konsole ausgeben
🖨️

## Beispiel: CustomStringConvertible
```swift
struct Player: CustomStringConvertible {
    var name: String = "@twostraws"

    var description: String {
        return name
    }
}
```

Jetzt kann man schrieben:

```swift
print(player)
```

## Beispiel: CustomDebugStringConvertible
```swift
struct Player: CustomDebugStringConvertible {
    var name: String = "@twostraws"

    var debugDescription: String {
        return name
    }
}
```

Jetzt kann man schrieben:

```swift
debugPrint(player)
```

## Muss man beides implementieren?

- Nein, wenn man nur etwas von beidem implementiert, wird es jeweils für beide Fälle verwendet, also sowohl für `print` als auch für `debugPrint`
- Siehe auch separates Kapitel zu `print` und `debugPrint`

## Zweck
- Wie kann man einen eigenen Typ auf der Konsole ausgeben?
- Unterscheidung zwischen debugPrint und print

#learning unit# #guide