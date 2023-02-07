
# Strategy
♟️

- Konzept: „Pogramm to an interface“
- Mehrere Enten haben das gleiche Verhalten aber nicht alle
- Man lagert das `FlyBehaviour` und das `QuackBehaviour` in Interfaces oder abstrake Klassen aus.
- Die Duck-Oberklasse referenziert auf solche Behaviours
- Das Verhalten wird von den konkreten Klassen im Konstruktor gesetzt
- Beachte: Einer Strategy wird auch oft `this` mitgegeben. Eine `fly`-Methode muss zum Beispiel das Gewicht der Ente kennen.
- Rollen: 
	- **Context**: Die Klasse die die Strategy verwendet
	- **Stategy**: Das Interface / Abstrakte Klasse
	- **Concrete Strategy**: die Konkreten Klassen

## Zusammenfassung
- Zweck


#nur learning unit#