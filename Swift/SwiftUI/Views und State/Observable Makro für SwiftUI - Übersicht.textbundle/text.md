# Observable Makro für SwiftUI - Übersicht
👀

## Siehe

[https://troz.net/post/2023/swiftui-data-flow-2023/][1]

## View erstellt (owned) und verändert: @State

Früher: State und StateObject

```swift
struct MyView: View {
   @State var model1: MyModel = MyModel() //Klasse 
   @State var model2: MyModel = MyModel() //Struct
}
```


## View liest oder schreibt nur: var/let

Früher: @ObservedObject

```swift
struct MyView: View {
   var model1: MyModel //Klasse (read and write properties)
   var model2: MyModel //Struct (read-only)
}
```

## View bekommt und verändert: @Binding (Struct)

(War bereits früher @Binding)

```swift
struct MyView: View {
   @Binding var model2: MyModel
}
```


## Objekt mit dem man ein Binding erstellen kann: @Bindable

Eigentlich wie var/let, aber man kann aus dem beobachteten Objekt ein Binding erstellen. An der Observation selbst ändert sich nichts.

```swift
struct MyView: View {
   @Bindable var model1: MyModel

	//...
	MyView($model1.myProperty)
}
```


##  Zusammenfassung
- Wann verwendet man let, state, Binding und Bindable?



	 





[1]:	https://troz.net/post/2023/swiftui-data-flow-2023/

#learning unit#