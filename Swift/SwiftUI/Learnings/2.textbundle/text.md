# Learning: Änderungen an CoreDate


## Lösung

- Core Data Objekte sind Klassen und keine Structs
- Deshalb müssen sie mit `StateObject` oder `ObservedObject` beobachtet werden.

## Zusammenfassung
- Was ist die Lösung für das Problem?