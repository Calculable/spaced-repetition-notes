# Custom Binding
⛓️


```swift
let agreedToAll = Binding<Bool>(
	get: {
		agreedToTerms && agreedToPrivacyPolicy
	},
	set: {
		agreedToTerms = $0
		agreedToPrivacyPolicy = $0
	}
)
```

## Zusammenfassung

Wie macht man ein Custom Binding?

#learning unit#