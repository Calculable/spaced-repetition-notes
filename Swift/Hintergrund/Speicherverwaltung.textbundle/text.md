# Speicherverwaltung
🚮

- Automatic Reference Count (ARC)
- Automatic Reference Count (ARC) zählt mit, wie viele Referenzen es auf ein Objekt gibt.
- Der Compiler kümmert sich um **retain** (neue Referenz) und **release** (Referenz entfernen)
- Neue Objekte werden auf dem **Heap** abgelegt
- Wenn es auf ein Objekt keine Referenzen gibt, wird das Objekt aus dem Speicher gelöscht (keine Garantie, dass dies Sofort geschieht)
- Bevor dieses löschen geschieht, wird die `deinit-Methode` aufgerufen
- Problem: Wenn sich Objekte gegenseitig referezieren können sie nie entfernt werden
- Deshalb gibt es `weak` -Referenzen, um dieses Problem zu beheben
- Es gibt eine **Optimize Object Lifetime** Einstellung in Xcode. Damit werden Objekte schneller abgeräumt. Damit kann man Testen, ob man Bugs hat weil der Code zuvor nur Zufällig funktioniert hat weil die Objekte nicht sofort abgeräumt wurden.

## Zusammenfassung
- Wie heisst das Konzept, dass bei Swift verwendet wird
- Welches Problem kann auftreten?
- Wie wird dieses Problem vermieden?


#learning unit#