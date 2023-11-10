# Array anhand von Key Path sortieren

## Beispiel

```swift
var sorted: [Example] {
	return unsorted.sorted(using: KeyPathComparator(\.attribute))
}
```

## Zusammenfassung
- Code

#learning unit#