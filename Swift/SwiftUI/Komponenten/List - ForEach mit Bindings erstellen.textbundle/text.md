# List / ForEach mit Bindings erstellen
🔁

## Zweck

> This is important for the times when the content you’re showing for each item needs a binding to some of its data, such as list rows having a text field to edit a user’s name.

## Codebeispiel

```swift
@State private var users = [
    User(name: "Taylor"),
    User(name: "Justin"),
    User(name: "Adele")
]

var body: some View {
    List($users) { $user in
        Text(user.name)
        Spacer()
        Toggle("User has been contacted", isOn: $user.isContacted)
            .labelsHidden()
    }
}
```

## Zusammenfassung
- Zweck / Codebeispiel


#nur learning unit#