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

## Default Werte

- Es gibt kein Optional bei Primitiven Datentypen.
- Das kann problematisch sein, zum Beispiel bei Bool wenn man nicht weiss ob man jetzt den Standartwert zurückbekommen hat oder tatsächlich ein Wert des users.)

- Integer: 0
- Bool: False
- Float: 0.0
- Double: 0.0
- Object: Nil (der Datentyp ist Any?)


## Eigene Default-Werte speichern

```swift
let values =
	"country": "Spain",
	"capital": "Madrid"
]

UserDefaults.standard.register(defaults: values)
```

- Das wird niemals gespeicherte Werte überschreiben. 
- Man muss das jedes mal aufrufen, wenn die App gestartet wird!

##  Daten werden nicht sofort gespeichert

`set` speichert die Daten nicht sofort sondern es kann eine zeit dauern. Wenn man in dieser Zeit die App „kill“ dann werden keine Werte gespeichert.

## Siehe auch

`@AppStorage` wrapper


## Zusammenfassung
- Mit Property Wrapper für SwiftUI
- Ohne Property Wrapper: Wert lesen und schreiben

#learning unit#