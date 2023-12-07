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

Beachte: Es ist ein normaler Initializer mit zwei Closures als Parameter

## Zusammenfassung

Wie macht man ein Custom Binding?

#learning unit#