
# Adapter 🔌

## Zweck

- Oft in Swift verwendet
- Oft für Legacy Code

## Objektadapter

### Problem
- Man hat eine gegebene Klasse und will diese so verwenden, das sie einem bestimmten Interface entspricht
- Hier will man, dass die Klasse Y mit dem Interface/Klasse X kompatibel wird (evt. müsste der Pfeil von Adapter zu X eigentlich gestrichelt sein…)

### Lösung

- Man erstellt eine Adapterklasse
- Diese Adapterklasse verwendet die bereits existierende Klasse mit **Komposition**
- So kann man ein Interface oder eine Abstrakte Klasse (!) implementieren

![][image-1]

### Vorteile und Nachteile
- **Vorteil**: Der Benutzer sieht nur die API-Methoden
- **Vorteil**: Wenn man schon einen Adapter für eine Klasse hat, dann kann man diese Klasse auch gerade als Adapter für Unterklassen verwenden (z.B: mit Konfigurationsfile)
- **Nachteil**: Auch wenn man eine Methode 1:1 weitergibt muss man ein paar Zeilen Code schreiben

## Klassenadapter

### Lösung

- Genau das gleiche, doch statt **Komposition** verwendet man **Vererbung**

### Vorteile und Nachteile

- **Nachteil**: Der Benutzer kann nicht nur die API-Methoden auf der Klasse aufrufen, sondern auch alle anderen Methoden (Beispiel in Java: Stack erweitert den Vektor, obwohl man eigentlich gewisse Methoden wie `insert at` gar nicht haben will…)
- **Nachteil**: Man kann so nur Interfaces nachbilden und natürlich keine abstrakten Klassen mehr `extenden` weil bereits ein `extend` gemacht wurde.
- **Vorteil**: Häufig spart man sich etwas aufwand, wenn gewisse Methodensignaturen bereits automatisch das Interface erfüllen, dann muss man es nämlich nicht mehr implementieren

	![][image-2]
	(Hier wäre ArrayList die inkompatible klasse und BikeStorerface das Interface von dem man will, das es durch die ArrayList erfüllt wird)

- **Nachteil**: Man muss explizit angeben, welche Klasse man erweitert und kann dann nicht einfach nur eine Unterklasse davon angeben (so wie beim Objektadapter)

	![][image-3]

## Zusammenfassung
- Zweck
- Welche zwei Arten von Adapter gibt es?
- Wie wird es implementiert?
- Vorteile / Nachteile

[image-1]:	assets/DraggedImage.tiff
[image-2]:	assets/DraggedImage-1.tiff
[image-3]:	assets/DraggedImage-2.tiff