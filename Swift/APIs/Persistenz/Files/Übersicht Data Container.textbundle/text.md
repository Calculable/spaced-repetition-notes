# Übersicht Data Container
📦

## Data Container
Jede App hat einen Data Container mit verschiedenen Ordnern:

![][image-1]

## Übersicht

| Verzeichnis                   | Files-App | iCloud-Sync / Backup | Automatisch Gelöscht |
| ----------------------------- | --------- | -------------------- | -------------------- |
| Documents                     | ✅         | ✅                    | ❌                    |
| Library / Application Support | ❌         | ✅                    | ❌                    |
| Library Cache                 | ❌         | ❌                    | ✅                    |
| tmp                           | ❌         | ❌                    | ✅                    |

## Document Directory

- **Beispiel**: `file:///Users/{USERNAME}/Library/Containers/{UUID}/Data/Documents/`
- Für Dateien, welche für den User sichtbar sein sollen. 
- Diese Dateien sind in der "Files"-App sichtbar
- Wird mit iCloud synchronisiert
- Ist im Backup enthalten
- Man kann auch Sub-Directories erstellen
- Man kann auch konfigurieren, dass die Dateien mit der eigenen App geöffnet werden (siehe hier: [https://swiftlyanand.medium.com/ios-storage-best-practices-294fca83ad9][1])

```swift
FileManager.default.urls(for: .documentDirectory, in: .userDomainMask).first
```


##  Library / Application Support
- **Beispiel: `file:///Users/{USERNAME}/Library/Containers/{UUID}/Data/Library/Application%20Support/"`**
- Nicht sichbar für den User
- z.B. das App-Datenbank-File
- Mit iCloud Synchronisiert
- Ist im Backup enthalten (Opt-Out ist möglich, [ulysses://x-callback-url/open?id=nzNr8E\_jepJSW1vdCIf1ww][2])
- Data Container
- iCloud Container

```swift
func pathForAppSupportDirectoryAsUrl() -> URL? {
    return try? FileManager.default.url(for: .applicationSupportDirectory, in: .userDomainMask, appropriateFor: nil, create: true)
}
```


> Unlike other directories mentioned here, “Application support” directory is not present by default in you application’s “Data container” and you need to create it first.

##  Library / Cache
- **Beispiel: `file:///Users/{USERNAME}/Library/Containers/{UUID}/Data/Library/Caches/`**
- Die Dateien hier können weggeworfen werden, wenn der Platz knapp ist (vom System). Das geschieht aber nicht während die App läuft
- Inhalt ist nicht im Backup enthalten

```swift
FileManager.default.urls(for: .cachesDirectory, in: .userDomainMask).first
```

## tmp
- **Beispiel: `file:///Users/{USERNAME}/Library/Containers/{UUID}/Data/tmp/`**
- Dateien die man nur für einen Kurzen Zeitraum braucht
- Wird vom System von Zeit zu Zeit aufgeräumt
- Aber es ist best-practice die Dateien selbst zu löschen, wenn man sie nicht mehr braucht

```swift
FileManager.default.temporaryDirectory
```

##  Datei vom Backup ausnehmen

Siehe: [ulysses://x-callback-url/open?id=nzNr8E\_jepJSW1vdCIf1ww][3]

## App Container herunterladen
Siehe: [ulysses://x-callback-url/open?id=Umda1Q\_O7fsnHKj4RnEHow][4]

## Zusammenfassung
- Wozu sind die Ordner Documents, Application Support, Cache und TMP geeignet?


[1]:	https://swiftlyanand.medium.com/ios-storage-best-practices-294fca83ad9
[2]:	ulysses://x-callback-url/open?id=nzNr8E_jepJSW1vdCIf1ww
[3]:	ulysses://x-callback-url/open?id=nzNr8E_jepJSW1vdCIf1ww
[4]:	ulysses://x-callback-url/open?id=Umda1Q_O7fsnHKj4RnEHow

[image-1]:	assets/DraggedImage.png

#learning unit# #guide