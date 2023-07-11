# Any / Existential Type vs. Generics
🌫️

## Um was geht es?
 - Wenn man ein Protokoll als Paramtertyp verwendet
- Früher war das Keyword `any` optional, mit Swift 6 wird es verpflichtet

## Beispiel: Existential Type

```swift
func collides(with: any Shape) -> Bool
```

- Mit `any` wird deutlich gemacht, dass es Performance-Einbussen gibt
- Dafür kann man zur Laufzeit eine beliebige Implementation haben

##  Alternative: Generics

Performanter wären Generics:

```swift
func collides<Other: Shape>(with: Other) -> Bool
```

gleichwertige Syntax:

```swift
func collides(with: some Shape) -> Bool
```

- Hier muss man aber bereits zur Compilezeit wissen, welcher Konkrete Typ man in die Funktion gibt.

## Zusammenfassung
- Beispiel: Eine Funktion möchte einen Shape (Protokoll) als Parameter entgegennehmen. Wie macht man das mit Existential Type und mit Generics (2 gleichwertige Varianten)? 
- Was sind die Unterschiede?

#learning unit#