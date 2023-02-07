# Constraints im Code
⛓️

## Beispiel: Anchors

```swift
NSLayoutConstraint.activate([
    childView.leadingAnchor.constraint(equalTo: parentView.leadingAnchor),
    childView.trailingAnchor.constraint(equalTo: parentView.trailingAnchor),
    childView.topAnchor.constraint(equalTo: parentView.topAnchor),
    childView.bottomAnchor.constraint(equalTo: parentView.bottomAnchor)
])
```

## Weitere Informationen

[The Auto Layout cheat sheet – Hacking with Swift][1]

## Zusammenfassung
- (ohne Exakten Code)
- Wie werden Constraints über den Code erstellt?

[1]:	https://www.hackingwithswift.com/articles/140/the-auto-layout-cheat-sheet

#nur learning unit#