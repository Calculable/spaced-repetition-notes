# Tasks für eine Zeit pausieren
💤

Mit Hilfe von Block und Duration:

```swift
try await Task.sleep(until: .now +  .seconds(1), clock: .continuous)
```

- Das bedeutet, dass es MINDESTENS 1 Sekunde schläft
- Es ist nie weniger, es kann aber auch etwas mehr sein

Man kann auch eine Toleranz angeben, was weniger Energie benötigt:

```swift
try await Task.sleep(until: .now + .seconds(1), tolerance: .seconds(0.5), clock: .continuous)
```

- Wenn man sleep auf einem „cancelled“ Task aufruft, wird ein Fehler geworfen
- Der Thread, welcher den Task ausführt, kann mit einem anderen Task fortfahren (bei `Thread.sleep()` ist das hingegen nicht der Fall)

## Alte API

Könnte in Zukunft Deprecated werden:

```swift
try await Task.sleep(nanoseconds: 1_000_000_000)
```


## Zusammenfassung
- Wie kann man einen Task für eine Sekunde pausieren?
- Was für eine Auswirkung hat das auf das System? 

#learning unit#