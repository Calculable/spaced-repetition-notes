# Begriff: Copy on Write 🖨️

## Definition
Structs werden kopiert. Allerdings gibt es eine Optimierung: Wenn ein Struct einer neuen Variable zugewiesen wird, dann bleibt es im Hintergrund so lange eine Referenz wie man nur lesend darauf zugreift. So wird unnötige Kopier-Arbeit vermieden.

Beachte: Arrays und Dictionaries sind auch structs!

##  Zusammenfassung
- Was bedeutet Copy on Write?