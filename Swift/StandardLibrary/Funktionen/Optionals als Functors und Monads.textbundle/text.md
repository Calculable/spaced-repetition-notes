# Optionals als Functors und Monads
🫙

## Map

Damit spart man sich die Prüfung, ob es Null ist oder nicht:

```swift
string.map { String($0.reversed()) }
```

## Flat Map

Manchmal würde man mit `map` ein Optional-Optional bekommen. Hier könnte zum Beispiel das `init` fehschlagen:

```swift
let latestScore = scores.last.map(Int.init)
```

Um das zu verhindern verwendet man `flatMap`:

```swift
let latestScore = scores.last.flatMap(Int.init)
```

## Hinweis

- Dieses Verhalten gilt auch für den Typ `Result`

## Zusammenfassung

- Was macht `map` auf einem Optional?
- Was macht `flatMap` auf einem Optional?
- Welcher Andere Typ ist ebenfalls ein Functor und ein Monad?
\- 


#learning unit#