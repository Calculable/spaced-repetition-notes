# Sheets: mit Optional
📃

## Anzeigen: mit Optional

Statt einem Boolean kann man auch ein Optional verwenden: ::!::

```swift
@State private var selectedUser: User? = nil
```

```swift
    .sheet(item: $selectedUser) { user in
        Text(user.id)
    }
```

## Zusammenfassung
wie macht man ein Sheet mit Optional?


#learning unit#