# Übersicht Property Wrappers für State
☁️

## @State (Struct)

> Use  `@State`  when your view needs to mutate one of its OWN properties 

```swift
@State private var isHighlighted = false
```

```swift
.alert(isPresented: $isHighlighted ) {
	//...
}
```

## @Binding (Struct!)

> Use  `@Binding`  when your view needs to mutate a property owned by an ancestor view

=\> Achtung - funktioniert bei Structs!

## @ObservedObject (ObservableObject Class)

> Use  `@ObservedObject`  when your view is dependent on an observable object that it can create itself, or that can be passed into that view’s initializer.

## @StateObject (ObservableObject Class)

> The rule is this: whichever view is the first to create your object must use `@StateObject`, to tell SwiftUI it is the owner of the data and is responsible for keeping it alive. All other views must use `@ObservedObject`, to tell SwiftUI they want to watch the object for changes but don’t own it directly.

## Zusammenfassung
- State
- Binding
- ObservedObject
- State Object



#nur learning unit#