# Dateien lesen 🤓
::28.2::

##  Datei lesen

(haben wir bereits gesehen mit „contentsOf“)

```swift
do {
	let input = try String(contentsOf: url)
} catch {
	print(error.localizedDescription)
}
```

## Zusammenfassung
- Datei lesen