# .onChange Modifier
📸

## Anwendungsfall
**Änderungen des State beobachten**

`didSet` funktioniert nicht bei States, da man damit nicht den Wert sondern den Wrapper beobachtet. Wenn jedoch der Wert mithilfe eines Bindings verändert wird, dann wird `didSet` nicht ausgelöst (Siehe Kapitel Property Wrapper). Stattdessen schreibt man:

##  Lösung (iOS 17)

Man nimmt entweder keinen Parameter oder zwei Parameter entgegen

```swift
XY.onChange(of: blurAmount) {
	print("New value is \(blurAmount)")
}
```

(Es wird immer getriggert, egal an welchem Element es hängt)



```swift
.onChange(of: name) { oldValue, newValue in
	print("\(oldValue) -> \(newValue)")
}
```

Mit dem `initial` Flag kann man definieren, dass es auch getriggert wird, wenn die View angezeigt wird

```swift
.onChange(of: name, initial: true) {
	print("triggered")
}
```


##  Vor iOS 17

...hatte `onChange` einen Parameter

```swift
.onChange(of: name, initial: true) { newValue in
	print("triggered")
}
```

## Siehe auch
Kapitel **.onChange Modifier für Binding**

## Zusammenfassung
- Für was braucht man den Modifier?
- Wie wird er angewendet?
- Was ist neu seit iOS 17

#learning unit#