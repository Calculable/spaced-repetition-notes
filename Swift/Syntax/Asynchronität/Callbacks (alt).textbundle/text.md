# Callbacks (alt)
📞


## Codebeispiel

```swift
func doSomething(completion: @escaping ([String]) -> Void) {
	///...do something asynchroniously
	completion("")
}
```

Um asynchronen Code auszuführen hat man oft `DispatchQueue.global().async()` verwendet

## Fehlerbehandlung
Siehe Kapitel: Fehlerbehandlung bei Callbacks

##  Heutige Lösung
- Heute verwendet man dafür Async-Await Code und allenfalls Continuation um eine Brücke zwischen dem alten Code mit Callback und dem neuen `Async-Await` Code zu bauen

## Zusammenfassung
- Wie haben Funktionen mit Callback-Handler funktioniert
- Welche Lösung bevorzugt man heute?

#learning unit#