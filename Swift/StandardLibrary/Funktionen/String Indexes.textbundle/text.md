# String Indexes
📍

##  Einen bestimmten String-Index erhalten

```swift
let startIndex = name.startIndex

//beachte: Die Indexe sind nicht einfach Integer. Das heisst, man muss sie so verschieben:
let lastNameIndex = name.index(startIndex, offsetBy: +6)
```


## Zeichen innerhalb des Ranges extrahieren
```swift
let firstName = name[lastNameIndex..<name.endIndex]

//oder einzelner Buchstabe
let character = name[index]
```

## Index finden

```swift
let firstSpace = name.firstIndex(of: " ")
```


##  Alternative
Alternativ kann an den String auch in ein Character Array umwandeln:

```swift
Array(string)
```


## Zusammenfassung

- Beispiel: Der 6te Index eines Strings auslesen
- Substring für einen String-Range erhalten
- Was wäre eine Alternative dazu?

#learning unit#