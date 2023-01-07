# Keypaths 📍

## Um was geht es?
- Keypaths referenzieren ein Property und nicht den Property-Inhalt!

##  Beispiel
```swift
let nameKeyPath = \Starship.name
```

Damit kann man zum Beispiel dann wieder auf das Konkrete Property zugreifen: 

```swift
print(voyager[keyPath: nameKeyPath])
```

##  Zweck
- Wozu sind Keypaths da
- Wie wird ein Keypath gespeichert
- Wie wird mit einem Keypath ein Property ausgelesen?