# Tasks für eine Zeit pausieren
💤

```swift
try await Task.sleep(nanoseconds: 1_000_000_000)
```

- Das bedeutet, dass es MINDESTENS 1 Sekunde schläft
- Es ist nie weniger, es kann aber auch etwas mehr sein

- Wenn man sleep auf einem „cancelled“ Task aufruft, wird ein Fehler geworfen
- Der Thread, welcher den Task ausführt, kann mit einem anderen Task fortfahren (bei `Thread.sleep()` ist das hingegen nicht der Fall)

## Zusammenfassung
- Wie kann man einen Task für eine Sekunde pausieren?
- Was für eine Auswirkung hat das auf das System? 

#learning unit#