# Downcasting
🎭

## as? / as!
- `as?`, returns an optional value of the type you are trying to downcast to.
-  `as!`, attempts the downcast and force-unwraps the result as a single compound action

```swift
 if let movie = item as? Movie {
	print("Movie: \(movie.name), dir. \(movie.director)")
 }
```

Besonders Sinnvoll in Switch-Statements:

## Zusammenfassung
- Zwei Varianten

#learning unit#