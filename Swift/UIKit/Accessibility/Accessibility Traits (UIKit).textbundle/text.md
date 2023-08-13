# Accessibility Traits (UIKit)
🦮 

##  Einzelner Trait setzen

(Ersetzt bereits vorhandene Trait)
```swift
accessibilityTraits = .button
```

## Einen Trait hinzufügen / enfernen

Es handelt sich um eine Mitmask

```swift
optionView.accessibilityTraits.insert(.header)
optionView.accessibilityTraits.remove(.header)
```

##  Zusammenfassung
- Trait setzen
- Trait hinzufügen

#learning unit#