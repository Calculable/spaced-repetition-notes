# Generics: Contextual Extension / Conditional Conformance
✋

```swift
extension Container where Item == Int {
	//....
}
```

Man könnte das ganze auch so machen:

```swift
extension Container {
    func average() -> Double where Item == Int {
		//....
    }
}
```

## Zusammenfassung
- Extension mit Condition
- Funktion mit Condition

#learning unit#