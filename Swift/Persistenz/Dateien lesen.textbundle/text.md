# Dateien lesen
🤓

##  Datei lesen

(haben wir bereits gesehen mit „contentsOf“)

```swift
let url = URL(fileURLWithPath: "/Users/jan/Desktop/HelloWorld.txt") //beachte: kein try!

do {
	let input = try String(contentsOf: url)
} catch {
	print(error.localizedDescription)
}
```

![][image-1]

## Zusammenfassung
- URL mit einer lokalen Datei erstellen
- lokale Datei lesen

[image-1]:	assets/Bildschirmfoto%202023-12-05%20um%2007.48.29.png

#learning unit#