# Async Await ⏰
::29::

## Für was braucht man Asynchrone Methoden?

Man sagt damit, dass der Code während der Ausführung unterbrochen werden darf, damit ein anderer Code weiterlaufen kann.

## Asynchrone Funktion schreiben

(für ein Konkretes Beispiel, siehe das API Kapitel)
```swift
func loadData() async {

}
```

oder falls es eine Exception werfen kann

```swift
func loadData() async throws {

}
```
## Aufruf einer asynchronen Funktion

### ….innerhalb einer asynchronen Funktion

```swift
await loadData()
```

### …innerhalb einer synchronen Funktion

```swift
Task.init {
	do {
		 self.images = try await fetchImages()
    } catch {
    	// .. handle error
    }
}
```

Der folgende Code gibt zum Beispiel zuerst 1 und erst dann 2 aus:

```swift
Task.init {
	await printTwo()
}
print(1)
```

Hinweis: Das `.init` muss man nicht unbedingt schreiben

### Wenn eine View angezeigt wird

Add this modifier to the List now:

```swift
.task {
    await loadData()
}
```

- Das ist die asynchrone Version von `onAppear()`

## Mehrere asynchrone Funktionen parallel Ausführen

```swift
async let games = getGames()
async let players = getPlayers()
async let scores = getScores()
let everything = await [games, players, scores]
```


## Gleichnamige Sync- und Async-Funktionen

> If you have async and synchronous functions that can be called in the same way, Swift will prefer whichever one matches your current context – if the call site is currently async then Swift will call the async function, otherwise it will call the synchronous function.

## Zusammenfassung
Zweck
Syntax asynchrone Funktion
Aufruf: von async Code, von sync code, von SwiftUI
Mehrere Funktionen paralell ausführen
Naming-Convention