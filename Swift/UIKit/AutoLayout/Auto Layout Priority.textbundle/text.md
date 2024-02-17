# Auto Layout Priority
🥇

##  Wie funktionieren die Priorities?

- Von 1 bis 1000
- 1000 ist „Required“ (default Wert)
- Alles darunter ist Optional
- Das System arbeitet die Constraints gemäss ihrer Priority ab
- Wenn ein Constraint nicht erfüllt werden kann, wird trotzdem versucht, es so gut wie möglich einzuhalten.
- Wenn nicht alle Constraints eingehalten werden können, wird auf der Konsole eine Fehlermeldung angezeigt

> Unable to simultaneously satisfy constraints.

##  System Priorities

```swift
UILayoutPriority.required    // 1000
UILayoutPriority.defaultHigh // 750
UILayoutPriority.defaultLow  // 250
```

##  Beispiel

Man möchte dass ein Button 500 gross ist, aber noch wichtiger ist, dass er nicht grösser als seine Superview wird:

### Pseudocode:

```swift
button.width = 500              // priority: 999
button.width <= superview.width // priority: 1000
```

### UIKit
```swift
button.translatesAutoresizingMaskIntoConstraints = false

let widthConstraint = button.widthAnchor.constraint(equalToConstant: 300)
widthConstraint.priority = UILayoutPriority(999)
widthConstraint.isActive = true

let widthLessThanOrEqualConstraint = button.widthAnchor.constraint(lessThanOrEqualTo: superview.widthAnchor)
widthLessThanOrEqualConstraint.priority = UILayoutPriority.required // = 1000
widthLessThanOrEqualConstraint.isActive = true
```

### SnapKit

```swift
button.snp.makeConstraints { make in
    make.width.equalTo(300).priority(999)
    make.width.lessThanOrEqualToSuperview().priority(1000)
}
```

## Zusammenfassung
- Welchen Range gibt es und was ist die Bedeutung?

#learning unit#