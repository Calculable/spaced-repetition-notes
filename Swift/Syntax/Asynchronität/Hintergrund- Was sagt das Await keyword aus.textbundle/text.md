# Hintergrund: Was sagt das Await keyword aus?
✋

## Beispiel
```swift
try await URLSession.shared.decode(from: inboxURL)
```

## Bedeutung
- Es heisst: Hier ist ein potentielle „suspension point“
	- Das sind Punkte an denen die Codeausführung stoppen kann, um anderen Code im Thread auszuführen
- Beachte: Nur weil man Asynchronen Code verwendet heisst das nicht, dass das Programm auf mehreren Cores läuft


##  Zusammenfassung
- Was hat das Await Schlüsselwort für eine Bedeutung?

#learning unit#