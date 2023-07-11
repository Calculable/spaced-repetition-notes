# Performance von Existential Types
🦥

## Warum ist „Any“ so langsam?
- Verwendet man „Some“, so erstellt der Compiler verschiedene Varianten der gleichen Methode, welche mittels **static dispatch** aufgerufen werden kann (schnell)
- Bei Any hingegen wird **dynamic dispatch** verwendet (denn man weiss ja nicht, um welchen Typen es sich handelt) - das ist jedoch langsam

##  Zusammenfassung
- Warum ist „Any“ so langsam?

#learning unit#