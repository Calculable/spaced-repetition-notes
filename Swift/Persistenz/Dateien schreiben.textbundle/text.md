# Dateien schreiben
📝

## Datei schreiben

```swift
try jsonString.write(to: savePath, options:[.atomic, .completeFileProtection])
```

- Mit `.completeFileProtection` wird das File geschützt, solange das Gerät gesperrt ist
- Das bedeutet natürlich keine 100% Sicherheit

## Zusammenfassung
- String schreiben

#learning unit#