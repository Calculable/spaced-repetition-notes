# UserDefaults
::25::

## Werte speichern

```swift
UserDefaults.standard.set(self.tapCount, forKey: "Tap")
```
Hier sollte man nicht viele Daten speichern (weniger als 1 MB)

## Werte lesen

```swift
UserDefaults.standard.integer(forKey: "Tap")
```

## Keine Optionals

(Es ist kein Optional. Bei Integer bekommt man den Standartwert „0“ zurück. Das kann problematisch sein, zum Beispiel bei Bool wenn man nicht weiss ob man jetzt den Standartwert zurückbekommen hat oder tatsächlich ein Wert des users.)

##  Daten werden nicht sofort gespeichert

`set` speichert die Daten nicht sofort sondern es kann eine zeit dauern. Wenn man in dieser Zeit die App „kill“ dann werden keine Werte gespeichert.

##  `@AppStorage` Property Wrapper

```swift
@AppStorage("tapCount") private var tapCount = 0
```
- Der String Name ist optional
- Nur für kleine, primitive Daten

