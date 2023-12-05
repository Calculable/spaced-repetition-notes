# Documents Directory
📑

## Document Directory Pfad auslesen


```swift
 let pathUrl = FileManager.default.urls(for: .documentDirectory, in: .userDomainMask)[0]

```

Mann kann auf diese Art auch auf sehr viele weitere Directories zugreifen:

![][image-1]

## Resultat

### Auf iOS

```swift
file:///Users/{username}/Library/Containers/{uuid}/Data/Documents/
```
- Das synchronisiert automatisch mit iCloud!
- Die App’s laufen in einer Sandbox
- Wenn die App gelöscht wird, dann wird auch der Inhalt des Documents-Directory gelöscht.

### auf macOS (Konsole App)

```swift
file:///Users/{username}/Documents/ 
```

## Filepfad ergänzen

```swift
pathUrl.appendingPathComponent("message.txt")
```

## Zusammenfassung
- Pfad auslesen
- Pfad ergänzen

[image-1]:	assets/Bildschirmfoto%202023-12-03%20um%2010.03.50.png

#learning unit#