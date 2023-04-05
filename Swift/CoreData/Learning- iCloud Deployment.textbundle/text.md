# Learning: iCloud Deployment
🧠
## Problem
- Ich habe die iCloud Datenbank nicht auf „Production“ bereitstellt.
- Man macht dies über das Dashboard:

![][image-1]

> To prevent conflicts, you can’t delete record types or fields that are already in production. Every time you deploy the development schema, its additive changes merge into the production schema

Bei den Entitlements kann man einstellen, ob die App während der Entwicklung auf der Deployment oder Development Datenbank läuft



## Zusammenfassung
- Warum hat iCloud in der veröffentlichten Version nicht funktioniert?

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-04-04%20um%2011.25.22.png

#learning unit#