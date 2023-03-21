# KeyValuePairs
🧑‍🤝‍🧑

## Definition

```swift
KeyValuePairs<Key, Value>
```

## Unterschiede zum Dictionary
Eine Alternative zum Dictionary mit folgenden Unterschieden:

- Key muss nicht zu `Hashable` konform sein
- Doppelte Keys sind erlaubt
- Die Reihenfolge, in der die Werte hinzugefügt wurden bleibt bestehen.


## Beispiel

```swift
let pairsWithDuplicateKey: KeyValuePairs<String, String> = [
    "天": "Heaven",
    "澤": "Lake",
    "澤": "Marsh",
	]
```


## Nachteil
- Die Collection ist nicht mutable nachdem man sie einmal mit dem Initializer erstellt hat
- Man kann nicht einzelne Werte auslesen, sondern muss das ganze zuerst umwandeln (map funktioniert)

##  Zusammenfassung
- Was sind unterschiede zum Dictionary
- Nachteil

#learning unit#