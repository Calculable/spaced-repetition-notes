# Bei einem Custom Control die Accessibility eines bestehenden System-Controls erben
🦮

```swift
MyCustomStepper(/*...*/)
	.accessibilityRepresentation {
		Stepper("Smoothie Count", value: Svalue, in: configuration.minValue...configuration.maxValue, step: configuration.increment)
}
```


## Zusammenfassung
- Wie heisst der Modifier?

#learning unit#