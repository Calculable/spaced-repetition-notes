# Observable Makro für SwiftUI - Bindable
🖇️

## Wozu wird es benötigt?

- Funktioniert nur für @Observable Klassen
- Das wird verwenet, wenn man aus den Properties bindings machen möchte
- Es ändert nichts an der Observation
- Wenn man keine Bindings benötigt, kann man auch einfach `var` verwenden.

##  View 1
```swift
@State private var donut = Donut()
//....
View2(donut) //beachte: Kein $
```

##  View 2

```swift
@Bindable var donut: Donut
//....
Textfield($donut.name) //Beachte: Mit $!
```

## Zusammenfassung
- Syntax, Wozu wird es verwendet

#learning unit#