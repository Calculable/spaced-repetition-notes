# Main Actor
🤴

- Es geht darum, dass alle Änderungen, die eine Auswirkung auf das UI haben, im Main Actor geschehen müssen
- In der Regel sorgt man dafür, dass der ganze View / ViewModel Code im Main Actor läuft. 
- Manchmal ist es aber nötig, den Main-Actor explizit aufzurufen. Zum Beispiel wenn man libraries hat, welche einen Closure entgegennehmen und diesen dann in einem anderen Kontext ausführen: 

```swift
await MainActor.run {
    // your work here
}

//früher: DispatchQueue.main.async
```

- Man kann auch Werte zurückgeben
- Man kann auch Funktionen oder Klassen mit `@MainActor` auszeichnen:


```swift
@MainActor
func display(scene: Scene)
```


## Zusammenfassung
- Zweck / Anwendungsfall
- Aufruf

#learning unit#