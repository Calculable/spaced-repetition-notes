# String Regex Funktionen  🧿

## Matches?

```swift
let hasMatch = input.wholeMatch(of: regex)  != nil
```


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

## Replacing

```swift
print(message.replacing(/[a-m]at/, with: "dog"))
```

## Informationen extrahieren

```swift
let message = "the cat sat on the mata"

let search1 = /the (.*) sat on the (.*)/

if let result = try? search1.wholeMatch(in: message) {
    print("\(result.1)") //cat
    print("\(result.2)") //mat
}
```

Hinweis: `result.0` gibt den ganzen gematchten String zurück

=\> Das könnte man noch schöner machen mit dem RegexBuilder. Siehe:

[https://www.hackingwithswift.com/swift/5.7/regexes][1]


## Zusammenfassung
- Prüfen, ob der ganze String matcht
- Gematchte Ranges zurückgeben
- Gematchte Substrings zurückgeben
- Ersetzen mit Regex
- Einzelne Informationen extrahieren mit Regex

[1]:	https://www.hackingwithswift.com/swift/5.7/regexes