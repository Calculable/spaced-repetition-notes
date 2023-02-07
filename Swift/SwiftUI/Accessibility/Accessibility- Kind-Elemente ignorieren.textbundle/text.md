# Accessibility: Kind-Elemente ignorieren
🦮

```swift
VStack {
    Text("Your score is")
    Text("1000")
        .font(.title)
}
.accessibilityElement(children: .ignore) //ignore ist der default parameter
.accessibilityLabel("Your score is 1000")
```

## Zusammenfassung
- Kinder ignorieren
