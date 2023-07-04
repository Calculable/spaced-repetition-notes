# Continuation
🌉

## Zweck
- Mit Continuations kann man eine Brücke zwischen altem Callback-Code und neuem Async-Await Code (Seit Swift 5.5) bauen.
- Besser wäre es den Code generell umzuschreiben, aber die Continuations sind eine Art Zwischenlösung

## Varianten
- `withCheckedContinuation()`
- `withCheckedThrowingContinuation()`


## Regeln
- Hinweis: Die Funktion MUSS die Continuation exakt einmal aufrufen

## Unsafe Varianten

Die normalen Varianten prüfen dass eine Continuation pro Durchlauf exakt einmal ausgeführt wird. Ist dies nicht der Fall, wird eine Warnung ausgegeben, weil es zu Ressourcenlecks führt.

Wenn man bewusst auf diesen Check verzichten möchte (z.B. aus Performancegründen) kann man dazu die Unsafe Varianten verwenden:

- `withUnsafeContinuation()`
- `withUnsafeThrowingContinuation()`

## Codebeispiel

```swift
func fetchInbox() async throws -> [Message] {
    try await withCheckedThrowingContinuation { continuation in
        fetchInbox { result in
            switch result {
            case .success(let messages):
                continuation.resume(returning: messages)
            case .failure(let error):
                continuation.resume(throwing: error)
            }
        }
    }
}
```

## Zusammenfassung
- Beispiel: Eine geprüfte Continuation, welche eine Callback-Funktion in eine async Funktion umwandelt (Rückgabewert: [Message]())



#learning unit#