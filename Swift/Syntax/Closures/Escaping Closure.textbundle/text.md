# Escaping Closure
📞

## @Escaping Closure

- wenn man ein closure übergibt und dies nicht sofort verwendet wird, dann kennzeichnet man es mit `@Escaping`

- Beispiel: Wir übergeben dem Initializer ein Closure. Dieses wird allerdings nicht direkt im initializer verwendet sondern an einer anderen Stelle. Deshalb wird es mit `@Escaping` annotiert.

## Zusammenfassung
Escaping Closure