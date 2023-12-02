# Info.plist
📄

## Wo liegt das File?
- Definiert in `Build Settings -> Info.plist File`

##  Zweck

- Die Infos werden zur Laufzeit benötigt (nicht direkt zum Compilieren oder Builden)
- Enthält Infos wie:
	- App Identifier, Versionsnummer, App Name
	- Capabilities
	- App Icons and Launch Images
	- Privacy Settings
## Info.plist bearbeiten

=\> Alle Varianten referenzieren die gleichen Infos. Manchmal wird das UI nicht immer sofort aktualisiert und man muss zuerst Xcode neu starten

### Custom iOS Target Properties

![][image-1]

Hinweis: Manchmal ist das File erst dann sichtbar, wenn man hier ein Custom Property eingetragen hat

### File als Property List

![][image-2]

### File als Source Code

![][image-3]

## Zusammenfassung
- Welche 2 Varianten gibt es, um das Info.plist File zu bearbeiten

[image-1]:	assets/Bildschirmfoto%202023-07-27%20um%2012.19.51.png
[image-2]:	assets/Bildschirmfoto%202023-07-27%20um%2012.17.22.png
[image-3]:	assets/Bildschirmfoto%202023-07-27%20um%2012.20.06.png

#learning unit#