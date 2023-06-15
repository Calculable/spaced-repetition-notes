# Learning: @ObservedObject funktioniert nicht mit optionaler Klasse
🧠

## Problem
Das hat nicht funktioniert (Location ist eine Klasse):

```swift
@ObservedObject var selectedLocation: Location?
```

## Lösung

Der Typ ist eigentlich ein Optional, also ein Struct:

```swift
@State var selectedLocation: Location?
```

##  Zusammenfassung
- Lösung

#learning unit#