# Auto Closure
📞

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

## Zusammenfassung
Auto-closure

#learning unit#