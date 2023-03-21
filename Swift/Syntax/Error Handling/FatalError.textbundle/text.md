# FatalError
💥

- Fatal Error führt zum Programmabsturz - Egal, welche Optimierung man verwendet 
- Das kann man verwenden, wenn die App bei einem Error nicht funktionieren kann
- Zum Beispiel weil ein File nicht gefunden worden kann - weil wir vergessen haben es zu inkludieren
- Ist für Fehler vorgesehen, die in der praktischen Anwendung niemals auftreten sollen (also für Programmierfehler) und von denen sich das Programm auch nicht erholen kann

```swift
fatalError("Could not load start.txt from bundle.")
```

## Zusammenfassung
 - Anwendungsfall
- Syntax

#learning unit#