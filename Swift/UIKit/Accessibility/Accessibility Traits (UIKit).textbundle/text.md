# Accessibility Traits (UIKit)
🦮 

##  Einzelner Trait setzen

(Ersetzt bereits vorhandene Trait)
```swift
myView.accessibilityTraits = .button
```

## Einen Trait hinzufügen / enfernen

Es handelt sich um eine Bitmask

```swift
myView.accessibilityTraits.insert(.header)
myView.accessibilityTraits.remove(.header)
```

##  Zusammenfassung
- Trait setzen: Ein Element soll ein Button sein
- Trait hinzufügen: Ein Element soll zusätzlich ein header sein

#learning unit#