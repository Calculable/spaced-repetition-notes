# Accessibility: Kind-Elemente kombinieren
🦮

```swift
VStack {
    Text("Your score is")
    Text("1000")
        .font(.title)
}
.accessibilityElement(children: .combine)
.accessibilityLabel("Your score is 1000")
```

## Zusammenfassung
- Kinder gruppieren


#learning unit#