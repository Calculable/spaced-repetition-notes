# Swift Data - Auf den Model Context zugreifen
💽

## Model Context erhalten (mit SwiftUI)

```swift
struct ContextView : View {
    @Environment(\.modelContext) private var context
}
```


## Model Context erhalten (ohne SwiftUI)

```swift
let context = ModelContext(container)
```

Wenn man durch die Änderung das UI aktualisieren möchte, kann man dies mit einem Kontext tun, der als MainActor läuft (ausserhalb der ViewHierarchie braucht man das):

```swift
container.mainContext
```

> Autosave is disabled for model contexts created by hand.

## Zusammenfassung
- Code (nur SwiftUI)

#learning unit#