# Transition
🐰

```swift
if isShowingRed {
	Rectangle()
		.transition(.asymmetric(insertion: .scale, removal: .opacity))
}
```

Damit es funktioniert, muss man hier eine Animation verwenden:

```swift
withAnimation {
	isShowingRed.toggle()
}
```

## Zusammenfassung
(ohne Details)

#learning unit#