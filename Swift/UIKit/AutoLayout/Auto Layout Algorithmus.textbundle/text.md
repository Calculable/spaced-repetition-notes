# Auto Layout Algorithmus
🧮
- Jeder Constraint ist eigentlich eine Lineare Gleichung
	- Beispiel: `button.leading = rootView.trailing * (factor: 0.5) + (offset: 8)`
- Das System geht folgendermassen vor:
	1. Priorität = 1000
		2. Gleichungssystem für alle Constraints mit entsprechender Priorität Lösen
		3. Ist das Layout mehrdeutig
			1. Ja =\> Priorität -= 1 =\> Bei Schritt 2 weitermachen
			2. Nein =\> Fertig

- Wenn ein Optionaler Constraint nicht erfüllt werden kann versucht das System trotzdem, so nahe wie möglich den Constraint zu erfüllen!

##  Quelle
[https://mischa-hildebrand.de/en/2017/11/the-auto-layout-comprehendium/][1]


## Zusammenfassung
- Konzept: Wie funktioniert der Auto Layout Algorithmus

[1]:	https://mischa-hildebrand.de/en/2017/11/the-auto-layout-comprehendium/

#learning unit#