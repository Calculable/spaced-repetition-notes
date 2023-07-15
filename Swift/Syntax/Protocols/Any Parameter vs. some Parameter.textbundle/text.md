# Any Parameter vs. some Parameter
🌫️

## Um was geht es?
 - Wenn man ein Protokoll als Paramtertyp verwendet
- Früher war das Keyword `any` optional, mit Swift 6 wird es verpflichtet

## Beispiel: Any (Existential Type)

```swift
func collides(with: any Shape) -> Bool
```

- Mit `any` wird deutlich gemacht, dass es Performance-Einbussen gibt
- Dafür kann man zur Laufzeit eine beliebige Implementation haben


##  Alternative: Some (Opaque Type)

Bei `some` Hingegen muss man bereits zur Compile-Zeit wissen, welchen Typ man bekommt


```swift
func collides(with: some Shape) -> Bool
```

Siehe auch: [ulysses://x-callback-url/open?id=WY28NQUX3V6DfidVyCoHgw][1]

## Zusammenfassung
- Was ist der Unterschied zwischen `any` und `some` bei der Funktionsdefinition

[1]:	ulysses://x-callback-url/open?id=WY28NQUX3V6DfidVyCoHgw

#learning unit#