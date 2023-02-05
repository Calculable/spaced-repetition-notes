# Mehrere asynchrone Funktionen parallel ausführen ⏰

```swift
async let games = getGames()
async let players = getPlayers()
async let scores = getScores()
let everything = await [games, players, scores]
```

## Zusammenfassung
- Codebeispiel