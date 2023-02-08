# Operators als first class types
🥇

## Was sind first class types?
- "First Class Types" bedeutet zum Beispiel dass man es in einer Variable speichern kann, oder es als Rückgabewert oder Funktions-Argument verwenden kann.
- Zum Beispiel sind in Swift Funktionen ein "First Class Type"
- Aber auch Operatoren sind "First Class Types":

## Beispiel

```swift
let add: (Int, Int) -> Int = (+)
print(add(1, 5))
```
- Beachte: Bei Operatoren sind in diesem Fall die runden Klammern notwendig.
- Beachte: Man muss hier explizit den Typ angeben, weil man mit `+` ja verschiedene Typen addieren kann.

## Tipp: Operatoren als alternative zu eigenem Closure

Das folgende Closure:

```swift
let sortedNames = names.sorted(by: { $0 > $1 })
//bzw.
let sortedNames = names.sorted { $0 > $1 }
```

kann man einfach ersetzen durch:

```swift
let sortedNames = names.sorted(by: >)    
```


## Zusammenfassung
Wie kann man Operatoren als First-Class-Types verwenden?


#nur learning unit#