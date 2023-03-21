
# Objektadapter
🔌

## Problem
- Man hat eine gegebene Klasse und will diese so verwenden, das sie einem bestimmten Interface entspricht
- Hier will man, dass die Klasse Y mit dem Interface/Klasse X kompatibel wird (evt. müsste der Pfeil von Adapter zu X eigentlich gestrichelt sein…)

## Lösung

- Man erstellt eine Adapterklasse
- Diese Adapterklasse verwendet die bereits existierende Klasse mit **Komposition**
- So kann man ein Interface oder eine Abstrakte Klasse (!) implementieren

![][image-1]

## Vorteile und Nachteile

=\> Siehe auch Klassenadapter

- **Vorteil**: Der Benutzer sieht nur die API-Methoden
- **Vorteil**: Wenn man schon einen Adapter für eine Klasse hat, dann kann man diese Klasse auch gerade als Adapter für Unterklassen verwenden (z.B: mit Konfigurationsfile)
- **Nachteil**: Auch wenn man eine Methode 1:1 weitergibt muss man ein paar Zeilen Code schreiben


## Zusammenfassung
- Zweck
- Wie wird es implementiert?
- Vorteile / Nachteile

[image-1]:	assets/DraggedImage.tiff

#learning unit#