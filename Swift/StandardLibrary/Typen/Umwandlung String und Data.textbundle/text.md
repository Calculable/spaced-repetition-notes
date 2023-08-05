# Umwandlung String und Data
⚙️

## Beispiel

```swift
let originalString = "Hello, World!"

// Convert the string to data using UTF-8 encoding.
let utf8Data = originalString.data(using: .utf8)!

// Convert the data back to a string using UTF-8 encoding.
let utf8String = String(data: utf8Data, encoding: .utf8)!
```

##  Warum muss man ein Encoding angeben?

- Data ist eine Binäre representation
- Je nach Encoding wird das gleiche Zeichen unterschiedlich als Bits/Bytes dargestellt

> For example, the UTF-8 encoding represents each character as one to four bytes, while the UTF-16 encoding represents each character as two or four bytes.

- Beachte: Unicode ist kein Encoding, sondern nur eine Zeichentabelle. UTF-8, UTF-16 und und UTF-32 sind alles Unicode Encoding. Es spielt keine Rolle was man beim Encoden wählt, solange man beim Decoden das gleiche verwendet. 

> UTF-8 encoding is a common choice because it'swidely used for web and text files.

##  Zusammenfassung
- String in Data umwandeln
- Data in String umwandeln
- Warum muss man ein Encoding angeben?

#learning unit#