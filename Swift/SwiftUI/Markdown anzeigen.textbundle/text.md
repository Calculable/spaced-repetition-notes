# Markdown anzeigen 📄

## Beispiel
Funktioniert direkt mit der Text-View:

```swift
Text("Visit Apple: [click here](https://apple.com)")
```

## Warum funktioniert es?
This automatic Markdown conversion happens because SwiftUI interprets those strings as being instances of `LocalizedStringKey`

Man kann auch explizite Instanzen erstellen:

```swift
 let markdownText: LocalizedStringKey = "* This is **bold** text, this is *italic* text, and this is ***bold, italic*** text."
```

## Was wenn man kein Markdown haben möchte?

```swift
Text(verbatim:)
```

## Zusammenfassung
- Beispielcode
- Warum funktioniert es?
- Was wenn man kein Markdown haben möchte?


#nur learning unit#