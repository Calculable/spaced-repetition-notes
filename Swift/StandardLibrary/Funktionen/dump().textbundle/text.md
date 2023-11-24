# dump()
🌀

- Wenn man kein debug String implementiert hat, gibt `print(myObject)` kein sinnvolles Resultat:

```swift
> MyClass 
```

- Mit `dump(myClass)` hingegen werden alle Properties ausgegeben:

```swift
MyClass
- example: "Test"
- example2: 2
```

- Funktioniert mit Klassen und Structs
- Es basiert NICHT auf `CustomStringConvertible` oder `CustomDebugStringConvertible` sondern arbeitet intern mit der Mirror API.

## Zusammenfassung
- Was macht `dump(myObject)`

#learning unit#