# Animation: an View binden
🚁


```swift
Button ("Tap Me") {
	animationAmount += 1
}
.scaleEffect(animationAmount)
.animation(.default, value: animationAmount)
```


## Zusammenfassung
- Immer animieren, wenn sich einen Variable ändert
