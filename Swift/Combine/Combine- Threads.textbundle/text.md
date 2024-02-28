# Combine: Threads
🔀

## Standartverhalten
- Standartmässig wird das Sink-Closure im gleichen Thread laufen, wie der Thread in welchem die Daten geposted werden.
- Zum Beispiel hatte ich das Problem, dass ich im Sink das UI aktualisiert habe, die Daten aber in einem Hintergrund-Thread gesendet wurden.

## Beispiel
Man kann angeben, in welcher Queue/Thread das Processing gemacht wird und das `sink` ausgeführt wird:

```
subscription = publisher
    // Specify that the subscription and any upstream processing should be done on a global background queue.
    .subscribe(on: DispatchQueue.global())
    // Apply some processing to the emitted values (e.g., multiply by 2).
    .map { value in
        //....
    }
    // Specify that the subscriber will receive values on the main queue.
    .receive(on: DispatchQueue.main)
    .sink{ value in
        //updaete UI
    }
```

- Beachte: `subscribe(on: )`, `receive(on: )`
- Wichtig, wenn man zum Beispiel mit den Werten etwas macht, was das UI verändern soll:** 
```swift
.receive(on: DispatchQueue.main)
```


## Zusammenfassung
- Standartverhalten: Auf welchem Thread werden im Combine-Framework die Werte empfangen?
- Wie kann man es immer auf dem Main-Thread empfangen?

#learning unit#