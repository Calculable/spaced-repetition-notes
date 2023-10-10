# Alert: mit Optional
🧩

## Beispiel
Beachte: Es braucht den Boolean noch immer

```swift
@State private var showingAlert = false
@State private var selectedUser: User? = nil
```

```swift
.alert("Welcome", isPresented: $isShowingUser, presenting: selectedUser) { user in
    Button(user.id) { }
} message: { user in
	Test("Hello World")
}
```

## Hinweis

- Anscheinend kann man nicht mehrere `alert` Modifier aneinander hängen.
- Lösung: Man hängt die Modifiers einfach an unterschiedliche Views.

## Zusammenfassung
- Wie macht man einen Alert mit Optional?


#learning unit#