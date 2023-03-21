# Map für Dictionary
📕
- Man kann man `map` auf einem Dictionary aufrufen
- Dabei iteriert man durch die Key-Value paare
- Das Resultat ist dann jedoch ein Array und kein Dictionary mehr
- Grund: Im Dictionary ist jeder Key einmalig. Je nachdem, wie man den Key transformiert ist dies jedoch nicht mehr sichergestellt.
- Deshalb gibt es für das Dictionary spezifische Versionen von `map`, die auch ein Dictionary zurückgeben:
	- `mapValues()`
	- `compactMapValues()`
- Die Keys bleiben dabei Identisch

## Zusammenfassung
- Warum gibt `map` auf einer Collection ein Array zurück?
- Wie kann man die Werte eines Dictionaries mappen, so dass das Resultat wiederum ein Dictionary ist?


#learning unit#