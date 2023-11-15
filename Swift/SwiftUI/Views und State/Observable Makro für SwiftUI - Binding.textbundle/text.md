# Observable Makro für SwiftUI - Binding
🖇️

## Um was geht es?

- Es ist nur für Structs wenn man das Model bekommt und verändern will.
- Man kann damit auch Bindings auf properties erstellen

## View 1

```swift
@State var donutModel = Donut()
//....
View2($donutModel)
```

## View 2

```swift
@Binding var donutModel: Donut //wird von aussen in die View gegeben

//...
donutModel = Donut() //möglich
Textfield("Example", text: $donutModel.name) //möglich
```


## Zusammenfassung
- Syntax, Wozu wird es verwendet

#learning unit#