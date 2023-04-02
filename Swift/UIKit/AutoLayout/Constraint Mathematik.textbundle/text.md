# Constraint Mathematik
🧮

## Berechnung
![][image-1]

Wenn man zum Beispiel will, dass eine View die hälfte der Parent-View ausfüllt, dann wählt man „Equal Height“ und setzt dann den multiplier auf 0.5

## Anwendung im Code (Beispiel)

```swift
answersLabel.widthAnchor.constraint
	equalTo: view.layoutMarginsGuide.widthAnchor,
	multiplier: 0.4,
	constant: -100
).isActive = true
```

## Zusammenfassung
- Wozu ist der Multiplier und die Konstante gut?
- Wie wird es im Code angewendet

[image-1]:	assets/Bildschirmfoto%202021-09-11%20um%2012.03.50.png

#learning unit#