# Layout nach Änderungen neu berechnen

=\> Häufig auch mit Animation, siehe separates Kapitel


```swift
self.view.layoutIfNeeded()
```

## Wann braucht man das?

- Zum Beispiel wenn man Animationen machen möchte
- Wenn man zum Beispiel die Constraints aktualisiert und sofort das neue Frame kennen will:

```swift
self.someSubviewConstraint.constant = newValue
self.view.layoutIfNeeded() // Forces layout update immediately
print(self.someSubview.frame) // Now the frame is updated
```

- Wenn man eine View als Bild exportieren möchte und sicher sein will, dass diese aktuell ist

=\> Achtung, die Funktion braucht viel Performance, man sollte sie nicht leichtfertig aufrufen.

## Zusammenfassung
- Wie kann man das Layout neu zeichnen lassen?

#learning unit#