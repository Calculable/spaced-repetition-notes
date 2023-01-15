# String Indexes 📍

## String Indexe
```swift
let startIndex = name.startIndex

//beachte: Die Indexe sind nicht einfach Integer. Das heisst, man muss sie so verschieben:
let lastNameIndex = name.index(startIndex, offsetBy: +6)
let endIndex = name.endIndex

let firstName = name[lastNameIndex..<name.endIndex]
```

## Index finden

```swift
let firstSpace = name.firstIndex(of: " ")
```

##  Einzelner Buchstabe

```swift
let character = name[index]
```

##  Alternative
Alternativ kann an den String auch in ein Character Array umwandeln:

```swift
Array(string)
```


## Zusammenfassung
- Wie kann man über einen Index-Range auf einen Teil des Strings zugreifen
- Was wäre eine Alternative dazu?