# @State und Threads
🔀

## @State-Variabeln dürfen aus einem Thread verändert werden

```swift
.task {
    do {
        inbox = try await fetchInbox()
    } catch {
        print(error.localizedDescription)
    }
}
```

Bei `await` kann es sein dass man im Main-Thread läuft oder auch in einem anderen Thread - man weiss es nicht. 

Aber bei @State-Variabeln wird automatisch eine synchronisierung vorgenommen.

=\> Aber ansonsten darf das UI nur aus dem Main-Thread editiert werden (auch Published-Variabeln dürfen nur aus dem Main-Thread bearbeitet werden)


## Zusammenfassung
- Wie kann man das UI aus einem Thread verändern?

#learning unit#