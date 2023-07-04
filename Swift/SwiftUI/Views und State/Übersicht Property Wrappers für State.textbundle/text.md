# Übersicht Property Wrappers für State
☁️

## @State (Struct)

- Wenn die View seine eigenen Properties verändert

```swift
@State private var isHighlighted = false
```

```swift
.alert(isPresented: $isHighlighted ) {
	//...
}
```

Tipp: Man kann auch Views mit `@State` beobachten.

## @Binding (Struct!)

> Use  `@Binding`  when your view needs to mutate a property owned by an ancestor view

- Wenn eine View ein Property verändern will, dass zu einer anderen View gehört

=\> Achtung - funktioniert bei Structs!

## @ObservedObject (ObservableObject Class)

- Wenn eine View eine Klasse beobachten möchte, die von aussen in die View kommt



## @StateObject (ObservableObject Class)

- Wenn eine View eine Klasse beobachten möchte, welche sie selbst erstellt (die View ist der Owner)


## Zusammenfassung
- State
- Binding
- ObservedObject
- State Object



#learning unit#