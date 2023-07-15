# Durch Enum Cases Iterieren
🔁
Mit `CaseIterable`:

```swift
enum Pasta: CaseIterable {
	case cannelloni, fusilli, linguine, tagliatelle
}
```

```swift
for shape in Pasta.allCases {
	print("I like eating \(shape).")
}
```

## Zusammenfassung
- Wie kann man schnell durch alle Cases eines Enums iterieren?

#learning unit#