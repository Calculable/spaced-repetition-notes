# Code Signing
✍️

## Zweck
- Als Entwickler muss man seine Builds signieren, um sie an den App Store oder an Beta Tester zu senden. Dank Codesigning weiss das System, dass die App nicht nachträglich verändert wurde und tatsächlich vom Entwickler stammt.

##  Was ist ein Zertifikat?
- Man signiert die App mit dem Private Key
- Im Zertifikat steht der Public Key
- Es gibt zwei Zertifikate: Development (für das eigene Gerät) und Distribution (für Testflight / App Store)
- Um eine App Signieren zu können, muss die Bundle ID im Developer Portal registriert sein

## Automatisches Codesigning
- Xcode kann es automatisch verwalten, wenn man mit dem Apple Developer Account angemeldet ist
- Auch CI/CD Tools können Zertifikate erstellen
- Es gibt auch Team Provisioning Profiles


## Manuelles Codesigning

- Hier erstellt man selbst ein Provisioning Profile und weisst dieses der Ap zu:
![][image-1]

- Ein Provisioning Profile enthält: Bundle ID + Zertifikat + App Capabilities
- Auch Hier gibt es Ad Hoc Profile und App Store / Testflight Profile
- Dies kann man im Apple Developer Portal erstellen


## Zusammenfassung
- Was ist ein Zertifikat?
- Was ist ein Provisioning Profile?

[image-1]:	assets/DraggedImage.png

#learning unit#