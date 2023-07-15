# dump()
🌀

Wenn man kein debug String implementiert hat, gibt `print(myObject)` kein sinnvolles Resultat:

```swift
> MyClass 
```

Mit `dump(myClass)` hingegen werden alle Properties ausgegeben:

```swift
MyClass
- example: "Test"
- example2: 2
```

Funktioniert mit Klassen und Structs

## Zusammenfassung
- Was macht `dump(myObject)`

#learning unit#