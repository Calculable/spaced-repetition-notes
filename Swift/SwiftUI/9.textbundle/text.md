# Custom Components 🧩
::9::

## Ohne `@Binding`
Man macht einfach seine eigene View-Klasse

```swift
struct CapsuleText: View {
    var text: String

    var body: some View {
        Text(text)
            .font(.largeTitle)
            .padding()
            .foregroundColor(.white)
            .background(.blue)
            .clipShape(Capsule())
    }
}
```

## Mit `@Binding`

- Wenn die Komponente nicht nur Darstellen soll, sondern auch Werte verändern

```swift
struct PushButton: View {
    let title: String
    @Binding var isOn: Bool //beachte: Binding, nicht state!

    var body: some View {
        Button(title) {
            isOn.toggle()
        }
        .shadow(radius: isOn ? 0 : 5)
    }
}
```

## Testen mit Constant-Binding

```swift
PushButton(title: "Remember Me", isOn: .constant(true))
```

## Zusammenfassung
- Custom Component ohne Binding
- Custom Component mit Binding
