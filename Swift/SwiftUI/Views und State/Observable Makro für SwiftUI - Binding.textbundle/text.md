# Observable Makro für SwiftUI - Binding
🖇️

## Wozu wird es benötigt?

- Das wird verwenet, wenn man aus den Properties bindings machen möchte
- Es ändert nichts an der Observation selbst

## View 1

```swift
@State var donutCount = Donut()
//....
View2($donutCount)
```

## View 2

```swift
@Binding var donutCount: Int //wird von aussen in die View gegeben
```


## Zusammenfassung
- Syntax, Wozu wird es verwendet

#learning unit#