# Snippet: Einen Baum elegant traversieren
👣

Hier hat man zum Beispiel einen Baum und möchte die Anzahl Elemente im ganzen Baum zählen:

```swift
var count: Int {
    1 + children.reduce(0) { $0 + $1.count }
}
```

Beachte: In `$0` steht das letzte Resultat, in `$1` jeweils eine Child-Node


## Zusammenfassung
- Code-Snippet: Wie kann man in einer Baumstruktur möglichst Elegant die Anzahl der Knoten zählen?


#nur learning unit#