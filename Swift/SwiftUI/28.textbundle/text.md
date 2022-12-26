# Documents Directory
::28::

## Document Directory Pfad auslesen


```swift
 let pathUrl = FileManager.default.urls(for: .documentDirectory, in: .userDomainMask)[0]

```

## Filepfad ergänzen

```swift
pathUrl.appendingPathComponent("message.txt")
```

## Datei schreiben

```swift
try jsonString.write(to: savePath, options:[.atomic, .completeFileProtection])
```

##  Datei lesen

(haben wir bereits gesehen mit „contentsOf“)

```swift
do {
	let input = try String(contentsOf: url)
} catch {
	print(error.localizedDescription)
}
```

##  Hinweis

- Das synchronisiert automatisch mit iCloud!
- Die App’s laufen in einer Sandbox
- Wenn die App gelöscht wird, dann wird auch der Inhalt des Documents-Directory gelöscht.


