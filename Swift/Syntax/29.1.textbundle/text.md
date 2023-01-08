# Mehrere Asynchrone Funktionen paralell ausführen ⏰
::29.1::

## Mehrere asynchrone Funktionen parallel Ausführen

```swift
async let games = getGames()
async let players = getPlayers()
async let scores = getScores()
let everything = await [games, players, scores]
```

## Zusammenfassung
- Codebeispiel