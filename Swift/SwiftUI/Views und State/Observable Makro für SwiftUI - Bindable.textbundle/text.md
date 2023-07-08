# Observable Makro für SwiftUI - Bindable
🖇️

## Klassen: @Bindable

###  View 1
```swift
@State private var donut = Donut()
//....
View2(donut) //beachte: Kein $
```


###  View 2

```swift
@Bindable var donut: Donut
//....
Textfield($donut.name) //Beachte: Mit $!
```

## Structs: @Binding
👀

### View 1

```swift
@State var donutCount = Donut()
//....
View2($donutCount)
```

### View 2

```swift
@Binding var donutCount: Int //wird von aussen in die View gegeben
```

## Zusammenfassung
- Wann braucht man State und wann Binding
- Was ist der Unterschied zwischen @Bindable und @Binding


#learning unit#