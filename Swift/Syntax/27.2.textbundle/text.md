# Any / Existential Type 🌫️
::27.2::
## Um was geht es?
 - Wenn man ein Protokoll als Paramtertyp verwendet
- Früher war das Keyword `any` optional, mit Swift 6 wird es verpflichtet
- Mit `any` wird deutlich gemacht, dass es Performance-Einbussen gibt


## Beispiel

```swift
func collides(with: any Shape) -> Bool
```

##  Alternativen

Performanter wären Generics:

```swift
func collides<Other: Shape>(with: Other) -> Bool
```

oder ein opaque parameter type:

```swift
func collides(with: some Shape) -> Bool
```

## Unterschied zwischen Any und Some und Generics

Mit „Some“ oder Generics ist es immer noch möglich, verschiedene Typen zu injecten (z.B. für testing). Das einzige was nicht möglich ist, ist die konkrete Implementation zur Laufzeit zu verändern.

```swift
var a: any Collection = [1,  2,  3]
a = ["a",  "b",  "c"]
```

## Warum ist „Any“ so langsam?

- Verwendet man „Some“, so erstellt der Compiler verschiedene Varianten der gleichen Methode, welche mittels `static dispatch` aufgerufen werden kann (schnell)
- Bei Any hingegen wird dynamic dispatch verwendet (denn man weiss ja nicht, um welchen Typen es sich handelt) - das ist jedoch langsam

## Zusammenfassung
Zweck
Anwenden
Alternativen (2)
Unterschiede zu den alternativen
Warum gibt es die Performance-Probleme?