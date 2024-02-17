# Frame einer View manuell setzen
🪟
- das Frame einer View wird durch die folgenden Werte bestimmt: `frame.origin.x`, `frame.origin.y`, `frame.size.width`, `frame.size.height`
- Um das Frame Manuell zu verändern muss man folgendes Setting aktivieren: `translatesAutoresizingMaskIntoConstraints = true` (ansonsten wird es einfach beim nächsten Layout Pass überschrieben)
	- Wenn man mit dem Interface Builder arbeitet ist `translatesAutoresizingMaskIntoConstraints` standartmässig `false`
	- Wenn man mit dem Interface Builder arbeitet ist `translatesAutoresizingMaskIntoConstraints` standartmässig `true`

## Zusammenfassung
- Ist das Frame Absolut oder Relativ?
- Was ist der Default-Wert von  translatesAutoresizingMaskIntoConstraints

#learning unit#