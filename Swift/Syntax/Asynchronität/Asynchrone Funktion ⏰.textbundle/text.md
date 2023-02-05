# Asynchrone Funktion ⏰

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


## Gleichnamige Sync- und Async-Funktionen

> If you have async and synchronous functions that can be called in the same way, Swift will prefer whichever one matches your current context – if the call site is currently async then Swift will call the async function, otherwise it will call the synchronous function.

## Siehe auch
- Aufruf einer Asynchronen Funktion

## Zusammenfassung
Zweck
Syntax asynchrone Funktion
Naming-Convention