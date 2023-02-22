# Versionierung
🔢

## Wie wird ein Build eindeutig identifiziert?

- **Build String** (CFBundleShortVersionString)
- **Version Number** (CFBundleVersion)

## Was ist der unterschied zwischen beiden?

CFBundleShortVersionString: Wird erhöht, wenn man es im App Store veröffentlicht. Ist nach aussen sichtbar

CFBundleVersion: Interne Versionsnummer. Wird bei jedem internen release erhöht.

![][image-1]

Für die CFBundleVersion heisst es zwar in der Dokumentation, man sollte drei Zahlen verwenden, in Wirklichkeit kann man jedoch irgendetwas verwenden.

##  Format

```swift
[Major].[Minor].[Patch]
```

##  Zusammenfassung
- Welche zwei Versionsnummer gibt es? Was ist der Unterschied
- Wie ist das Format?

[image-1]:	assets/HNrrs.jpg