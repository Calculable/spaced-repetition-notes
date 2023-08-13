# isAccessibilityElement = true
🦮 

## Wann wird es gesetzt?
- Für Custom UIControlls
- Für die Standard-Controlls ist das bereits automatisch der Fall
- Wenn wichtige Informationen dargestellt werden
- Wenn interaktive Aktionen ausgeführt werden können

> But usually, you make a container view an accessibility element by setting its isAccessibilityElement

## Default Wert
> The default value for this property is false unless the element is a standard UIKit control, in which case, the value is true.

## Beispiel
Im `init` der UIView: 

```swift
isAccessibilityElement = true
```

## SwiftUI Äquivalent
- `.accessibilityElement(...)`

##  Zusammenfassung
- Wann braucht man das?
- Was ist der Standart-Wert?

#learning unit#