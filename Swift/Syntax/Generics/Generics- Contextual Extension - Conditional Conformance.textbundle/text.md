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
- Beispiel: Man macht eine Extension für ein Container von Int werten
- Funktion mit Condition

#learning unit#