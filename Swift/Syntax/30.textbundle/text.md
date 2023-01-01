# Main Actor 🤴
::30::

- Es geht darum, dass alle Änderungen, die eine Auswirkung auf das UI haben, im Main Actor geschehen müssen
- In der Regel sorgt man dafür, dass der ganze View / ViewModel Code im Main Actor läuft. 
- Manchmal ist es aber nötig, den Main-Actor explizit aufzurufen. Zum Beispiel wenn man libraries hat, welche einen Closure entgegennehmen und diesen dann in einem anderen Kontext ausführen: 

```swift
await MainActor.run {
    // your work here
}
```

- Man kann auch Funktionen oder Klassen mit `@MainActor` auszeichnen

## Zusammenfassung
Zweck / Anwendungsfall
Aufruf