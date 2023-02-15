# LocalizedStringKey vs. NSLocalizedString
🌐

## NSLocalizedString

- Ist eine Abstraktionsebene tiefer als der LocalizedStringKey 
- Übersetzt den String direkt:

```swift
var projectTitle: String {
    title ?? NSLocalizedString("New Project", comment: "Create a new project")
}
```

Hier ist es besonders hilfreich, weil man ja nicht einen `LocalizedStringKey` als Rückgabewert mitgeben könnte, da sich der Titel vom Benutzer selbst anpassen lässt.

## LocalizedStringKey

Wir als eigener Typ verwendet:

```swift
var test: LocalizedStringKey  = "Hello World"
```

SwiftUI kümmert sich dann darum, es zu übersetzen:

```swift
Text(test)
```

## Zusammenfassung
- Was ist der Unterschied zwischen diesen beiden?


#nur learning unit#