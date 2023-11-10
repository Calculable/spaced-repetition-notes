# Observable Makro für SwiftUI - Bindable
🖇️

## Wozu wird es benötigt?

- Das wird verwenet, wenn man aus den Properties bindings machen möchte
- Es ändert nichts an der Observation

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