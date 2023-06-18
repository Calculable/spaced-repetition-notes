# .onChange Modifier
📸

## Anwendungsfall
**Änderungen des State beobachten**

`didSet` funktioniert nicht, da man damit nicht den Wert sondern den Wrapper beobachtet. Wenn jedoch der Wert mithilfe eines Bindings verändert wird, dann wird `didSet` nicht ausgelöst (Siehe Kapitel Property Wrapper). Stattdessen schreibt man:

##  Lösung

```swift
XY.onChange(of: blurAmount) { newValue in
	print("New value is \(newValue)")
}
```

(Es wird immer getriggert, egal an welchem Element es hängt)

##  Neuerungen mit iOS 17

- Neu hat das Closure entweder
	- Keinen Parameter: Man liest die Änderungen direkt aus der gesetzten Variable
	- Zwei Parameter: Mit dem alten und dem neuen Wert

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

## Siehe auch
Kapitel **.onChange Modifier für Binding**

## Zusammenfassung
- Für was braucht man den Modifier?
- Wie wird er angewendet?
- Was ist neu seit iOS 17

#learning unit#