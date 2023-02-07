# Regex: Matching Ranges / Substrings
🧿

## Matching Ranges

```swift
let message = "the cat sat on the mata"
let ranges = message.ranges(of: /.at/)
```

## Matches as Substrings

```swift
let message = "the cat sat on the mata"
let ranges = message.ranges(of: /.at/)

let result = ranges.map {message[$0]}
```

## Zusammenfassung
- Gematchte Ranges zurückgeben
- Gematchte Substrings zurückgeben


#nur learning unit#