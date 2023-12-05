# UIKit Animation Framework
🎦

```swift
setNeedsLayout()
heightConstraint?.constant = progress * bounds.height

UIView.animate(withDuration: 0.2) { [weak self] in
	self?.layoutIfNeeded() //animiert den veränderten Constraint

	//Weiteres Beispiel
	self.imageView.transform = CGAffineTransform(scaleX: 2, y: 2)
}
```

- Strenggenommen bräuchte man `[weak self]` nicht, weil das Closure sowieso gleich wieder weggeworfen wird.
- Das UIKit Animation Framework ist ein Wrapper um Core Animation.
- Man kann die Funktion auch noch weiter konfigurieren (delay, option, onFinished-Closure...)

## Zusammenfassung
- Code: Eine einfache animation

#learning unit#