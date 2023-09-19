# Threads bei Combine
🎭

## Standartverhalten
- Standartmässig wird das Sink-Closure im gleichen Thread laufen, wie der Thread in welchem die Daten geposted werden.
- Zum Beispiel hatte ich das Problem, dass ich im Sink das UI aktualisiert habe, die Daten aber in einem Hintergrund-Thread gesendet wurden.

## Daten im Main-Thread empfangen
```swift
myPublisher
	.receive(on: DispatchQueue.main)
	.sink { value in
		//do something
	}.store(in: &cancellables)
```

## Zusammenfassung
- Standartverhalten: Auf welchem Thread werden im Combine-Framework die Werte empfangen?
- Wie kann man es immer auf dem Main-Thread empfangen?

#learning unit#