# Speicherverwaltung
🚮

- Automatic Reference Count (ARC)
- Automatic Reference Count (ARC) zählt mit, wie viele Referenzen es auf ein Objekt gibt.
- Wenn es auf ein Objekt keine Referenzen gibt, wird das Objekt aus dem Speicher gelöscht
- Bevor dieses löschen geschieht, wird die `deinit-Methode` aufgerufen

- Problem: Wenn sich Objekte gegenseitig referezieren können sie nie entfernt werden
- Deshalb gibt es `weak` referenzen, um dieses Problem zu beheben

## Zusammenfassung
- Wie heisst das Konzept, dass bei Swift verwendet wird
- Welches Problem kann auftreten?
- Wie wird dieses Problem vermieden?


#learning unit#