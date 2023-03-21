# UserDefaults
💾

## Was ist UserDefaults.Standart?

In Advanced apps kann man eigene Versionen von UserDefaults erstellten. Für einfache Apps reicht Standart aus.

## Werte speichern

```swift
UserDefaults.standard.set(self.tapCount, forKey: "Tap")
```
Hier sollte man nicht viele Daten speichern (weniger als 1 MB)

## Werte lesen

```swift
UserDefaults.standard.integer(forKey: "Tap")
```

(Es ist kein Optional. Bei Integer bekommt man den Standartwert „0“ zurück. Das kann problematisch sein, zum Beispiel bei Bool wenn man nicht weiss ob man jetzt den Standartwert zurückbekommen hat oder tatsächlich ein Wert des users.)

## Keine Optionals

(Es ist kein Optional. Bei Integer bekommt man den Standartwert „0“ zurück. Das kann problematisch sein, zum Beispiel bei Bool wenn man nicht weiss ob man jetzt den Standartwert zurückbekommen hat oder tatsächlich ein Wert des users.)

##  Daten werden nicht sofort gespeichert

`set` speichert die Daten nicht sofort sondern es kann eine zeit dauern. Wenn man in dieser Zeit die App „kill“ dann werden keine Werte gespeichert.

## Siehe auch

`@AppStorage` wrapper

## Zusammenfassung
- Mit Property Wrapper
- Ohne Property Wrapper

#learning unit#