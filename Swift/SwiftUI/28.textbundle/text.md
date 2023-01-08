# Documents Directory 📑
::28::

## Document Directory Pfad auslesen


```swift
 let pathUrl = FileManager.default.urls(for: .documentDirectory, in: .userDomainMask)[0]

```

## Filepfad ergänzen

```swift
pathUrl.appendingPathComponent("message.txt")
```


##  Hinweis

- Das synchronisiert automatisch mit iCloud!
- Die App’s laufen in einer Sandbox
- Wenn die App gelöscht wird, dann wird auch der Inhalt des Documents-Directory gelöscht.

## Zusammenfassung
- Pfad auslesen
- Pfad ergänzen
