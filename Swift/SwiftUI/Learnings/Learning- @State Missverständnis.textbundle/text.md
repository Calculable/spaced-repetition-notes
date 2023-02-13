# Learning: @State Missverständnis
🧠

## Informationen
- @State bedeutet nicht, dass man ein Struct "beobachten" möchte
- Stattdessen bedeutet es, dass man innerhalb der View Änderungen am Struct vornehmen kann
- Möchte man hingegen nur lesend darauf zugreifen, kann man einfach eine normale Variable verwenden
- Das UI wird sowieso neu gezeichnet, weil die darüberliegende View bei einer Änderung die View neu zeichnet:

## Beispiel-Code

```swift
struct MyMainView {
	@State private var value = 5

	var body: some View {
		MySubView(value: value)
	}
}
struct MySubView {
	var value = 5

	var body: some View {
		Text("\(value)")
	}
}
```

## Zusammenfassung
- Wann braucht man `@State` und wann nicht?


#nur learning unit#