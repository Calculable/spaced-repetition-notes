# Capture List gemeinsam mit Parametern
🦋

##  Beispiel
```swift
writeToLog { [weak self, unowned taylor, adele] user, message in 
    self?.addToLog("\(user) triggered event: \(message)")
}
```

Achtung: Adele würde hier „strong“ capture verwenden.

## Zusammenfassung
Syntax

#learning unit#