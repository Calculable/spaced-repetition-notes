# String-Funktionen  ↩️


## Count

```swift
print(capitalA.count)
```

Es gibt auch spezifische Varianten:

```swift
print("🇵🇷") //2
```

## Has Prefix

```swift
let result = name.hasPrefix("Prefix")
```


## Has Suffix

```swift
let result = name.hasSuffix("Suffix")
```

## Prefix

```swift
let result = name.prefix(3)
```


## Suffix

```swift
let result = name.suffix(3)
```


## Split

```swift
let result = split(separator: ";")
```


Beachte: Das Resultat sind Substrings. Diese können mit `String(substring)` wieder in normale Strings konvertiert werden.

Optional kann man die beiden Attribute `omittingEmptySubsequences` und `maxSplits` setzen

## Zusammenfassung
- Count
- HasPrefix / HasSuffix
- Prefix / Suffix
- Split

#nur learning unit#