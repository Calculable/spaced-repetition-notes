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

## Siehe auch
Kapitel **.onChange Modifier für Binding**

## Zusammenfassung
- Für was braucht man den Modifier?
- Wie wird er angewendet?

#learning unit#