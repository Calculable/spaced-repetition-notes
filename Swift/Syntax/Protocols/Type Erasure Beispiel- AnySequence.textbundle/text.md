# Type Erasure Beispiel: AnySequence
❎

## Eine AnySequence erstellen

```swift
let seq = AnySequence<Int>([1,2,3])
//This creates an AnySequence<Int>.
```

- AnySequence ist kein Protokoll
- Sequence ist aber ein Protokoll das vom Array implementiert wird
- Sondern ein generisches Struct das eine andere Sequence wrappt

## Warum möchte man das machen?

- Beispiel: Man hat eine Funktion und möchte eine Sequenz von Integer als Parameter entgegennehmen
- Sequence ist jedoch ein Protokoll mit einem Associated Type. Man kann es also nicht so einfach als Parameter erwarten

## Weitere Typen
Es gibt weitere Typen wie `AnyView`, `AnySequence`


##  Zusammenfassung
- Wie erstellt man ein Objekt vom Typ AnySequence?
- Warum würde man das wollen

#learning unit#