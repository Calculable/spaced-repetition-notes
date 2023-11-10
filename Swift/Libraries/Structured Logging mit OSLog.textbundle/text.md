# Structured Logging mit OSLog
📜

##  Code
```swift
import OSLog
```

```swift
let logger = Logger(subsystem: "BackyardBirdsData", category: "Account")
```

- Subsystem: Oft Bundle identifier
- Kategorie: Oft Klassenname oder Komponentenname

```swift
logger.info("Logging in user '\(username)')
```

## Ausgabe

=\> Vorteil: Stacktrace, Codezeile etc. wird auch gleich automatisch geloggt und man kann Filtern

![][image-1]

## Zusammenfassung
- Import
- Logger erstellen
- Ausgabe

[image-1]:	assets/Bildschirmfoto%202023-06-09%20um%2014.19.44.png

#learning unit#