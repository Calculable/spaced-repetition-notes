# Funktionsparameter isolieren
📦

## Beispiel

```swift
actor MyData { //beachte: actor
    var title = "Anonymous"
    var names = [String]()
}

func debugLog(dataStore: isolated MyData) {
    print("Username: \(dataStore.title)")
    print("Friends: \(dataStore.names)")
}
```

Beachte: Das `isolated` Schlüsselwort

##  Was bringt das?

- Die Funktion muss nicht mehr bei jedem Zugriff auf den dataStore `await` verwenden

##  Was sind die Auswirkungen?

- Die ganze Funktion `debugLog` muss mit `await` aufgerufen werden (obwohl es kein `async` Keyword gibt)
- =\> Das „Problem“ wird also einfach eine Stufe höher geschoben

## Mehrere Funktionsparameter isolieren

- Ist nicht möglich


##  Zusammenfassung
- Code
- Zweck
- Auswirkung


#learning unit#