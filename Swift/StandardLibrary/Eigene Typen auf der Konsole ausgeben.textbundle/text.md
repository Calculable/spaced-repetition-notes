# Eigene Typen auf der Konsole ausgeben
🖨️

## Beispiel
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
print(player)
```


## Zweck
- Wie kann man einen eigenen Typ auf der Konsole ausgeben?