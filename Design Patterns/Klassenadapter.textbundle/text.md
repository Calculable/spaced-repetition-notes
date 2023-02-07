# Klassenadapter
🔌

## Lösung

- Genau das gleiche, doch statt **Komposition** verwendet man **Vererbung**

## Vorteile und Nachteile

- **Nachteil**: Der Benutzer kann nicht nur die API-Methoden auf der Klasse aufrufen, sondern auch alle anderen Methoden (Beispiel in Java: Stack erweitert den Vektor, obwohl man eigentlich gewisse Methoden wie `insert at` gar nicht haben will…)
- **Nachteil**: Man kann so nur Interfaces nachbilden und natürlich keine abstrakten Klassen mehr `extenden` weil bereits ein `extend` gemacht wurde.
- **Vorteil**: Häufig spart man sich etwas aufwand, wenn gewisse Methodensignaturen bereits automatisch das Interface erfüllen, dann muss man es nämlich nicht mehr implementieren

	![][image-1]
	(Hier wäre ArrayList die inkompatible klasse und BikeStorerface das Interface von dem man will, das es durch die ArrayList erfüllt wird)

- **Nachteil**: Man muss explizit angeben, welche Klasse man erweitert und kann dann nicht einfach nur eine Unterklasse davon angeben (so wie beim Objektadapter)

	![][image-2]

## Zusammenfassung
- Zweck
- Welche zwei Arten von Adapter gibt es?
- Wie wird es implementiert?
- Vorteile / Nachteile

[image-1]:	assets/DraggedImage-1.tiff
[image-2]:	assets/DraggedImage-2.tiff

#nur learning unit#