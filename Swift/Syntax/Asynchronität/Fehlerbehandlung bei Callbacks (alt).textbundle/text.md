# Fehlerbehandlung bei Callbacks (alt)
💥
- Statt mit `do-catch` arbeitet man mit dem Result Enum:

```swift
func fetchInbox(completion: @escaping (Result<[Message], Error>) -> Void)
```

##  Zusammenfassung
- Wie hat man früher bei Callbacks das Error-Handling implementiert?

#learning unit#