# unterschiedliche Views zurückgeben
🪟

## Lösung 1: Ternary Conditional Operator verwenden
```swift
Text("Hello, World!")
	.frame(width: Bool.random() ? 300 : nil)
```

(Anstelle von IF-Statements)

## Lösung 2: View in eine Gruppe packen
```swift
Group {
	//....
}
```

##  Lösung 3: `@ViewBuilder` annotation verwenden
```swift
@ViewBuilder var randomText: some View {...}
```


## Lösung 4: In AnyView wrappen

```swift
return AnyView(Text("Hello, World!"))
```

Sehr unperformant

## Zusammenfassung
- 4 Möglichkeiten um unterschiedliche Views zurückzugeben
- Wie funktioniert die Variante mit dem ViewBuilder?