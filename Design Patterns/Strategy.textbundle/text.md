
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


## Unterschied zum State Pattern

Das Strategy Pattern ist eine Alternative zum Vererben, Das State Pattern ist eine Alternative bei zu vielen Kontrollstrukturen.

## Zusammenfassung
- Zweck
- Unterschied zum State Pattern


#learning unit#