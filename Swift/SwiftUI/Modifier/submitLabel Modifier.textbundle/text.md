# .submitLabel Modifier

Damit kann man statt „Return“ einen anderen Text auf dem Keyboard anzeigen:

```swift
	TextField("First name", text: $firstName)
		.focused($focusedField, equals: .firstName)
		.submitLabel(.next)
```


#learning unit#