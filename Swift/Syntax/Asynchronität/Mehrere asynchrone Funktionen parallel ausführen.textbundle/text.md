# Mehrere asynchrone Funktionen parallel ausführen
⏰

## Beispiel
```swift
async let games = getGames() //beachte: kein await erforderlich
async let players = getPlayers()
async let scores = getScores()

//now it runs in paralell while we wait
let receivedGames = try await games
let receivedPlayes = try await players
let receivedScores = try await scores

//Alternativ: 
//let everything = try await [games, players, scores]
```

=\> Beachte Es funktioniert nur mit `let` damit keine DataRaces entstehen.

## Warum verwendet man diese Syntax?

Dieser Code wäre schlecht, weil die zweite Zeile erst dann laufen kann, wenn die erste Zeile abgeschlossen ist:


```swift
let games = try await getGames()
let players = try await getPlayers()
let scores = try await getScores()
```



## Zusammenfassung
- Codebeispiel
- Warum verwendet man diese Syntax?

#learning unit#