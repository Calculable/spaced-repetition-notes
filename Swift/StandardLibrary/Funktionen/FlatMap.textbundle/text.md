# FlatMap
🫓

## Beispiel

Macht aus einer verschachtelten Collection eine nicht-verschachtelte Collection:

```swift
let result = [[1, 2, 3], [4, 5, 6]]
    .flatMap { array in
        array.map { value in
            2*value
        }
    }
```

Beachte: Innerhalb des Closures für `flatMap` hat man Zugriff auf die einzelne Sub-Collection, nicht auf den einzelnen Value!

## Zusammenfassung
- Wie funktioniert flatMap?



#learning unit#