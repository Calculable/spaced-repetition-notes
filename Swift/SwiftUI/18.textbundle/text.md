# Sheets 📃
::18::

## Anzeigen: mit Boolean
```swift
struct ContentView: View {
    @State private var showingSheet = false

    var body: some View {
        Button("Show Sheet") {
            showingSheet.toggle()
        }
        .sheet(isPresented: $showingSheet) {
            SecondView()
        }
    }
}
```

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

## Dismiss

Aber man kann das Sheet über das Environment schliessen

```swift
@Environment(\.dismiss) var dismiss
```

```swift
Button("Dismiss") {
    dismiss()
}
```

## Zusammenfassung
Wie macht man ein Sheet mit Boolean?
wie macht man ein Sheet mit Optional?
Wie „dismisst“ man ein Sheet?