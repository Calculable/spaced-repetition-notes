# Auto Closure / Escaping Closure 📞
::8::

## Auto Closure

Beachte das folgende Beispiel:

```swift
func serve(customer customerProvider: @autoclosure () -> String) {
    print("Now serving \(customerProvider())!")
}
serve(customer: customersInLine.remove(at: 0))
// Prints "Now serving Ewa!"
```

Bei Serve sieht es so aus als würde man `remove` bereits aufrufen und car kein Closure mitgeben. Das ist aber nicht der Fall, weil man `@autoclosure` verwendet.

(Hinweis: Remove gibt das entferne Element zurück)

Nicht immer empfohlen

## @Escaping Closure

- wenn man ein closure übergibt und dies nicht sofort verwendet wird, dann kennzeichnet man es mit `@Escaping`

- Beispiel: Wir übergeben dem Initializer ein Closure. Dieses wird allerdings nicht direkt im initializer verwendet sondern an einer anderen Stelle. Deshalb wird es mit `@Escaping` annotiert.

## Zusammenfassung
Auto-closure, escaping Closure