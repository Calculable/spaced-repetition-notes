# Übersetzung: Was geschieht hinter den Kulissen?
💬

**Warum kann etwas wie `.navigationTitle("Hello World")` durch das Übersetzungsfile überschrieben werden?**

Weil diese Modifiers nicht einen String entgegennehmen, sondern auch einen `LocalizedStringKey`:

```swift
public func navigationTitle(_ titleKey: LocalizedStringKey) -> some View
public func navigationTitle<S>(_ title: S) -> some View where S : StringProtocol
```

Und der LocalizedStringKey lässt sich wiederum aus einem String-Literal erzeugen.

Die Übersetzungsfiles können auch mit String-Interpolation umgehen!

## Zusammenfassung
- Warum werden viele SwiftUI-Elemente wie Text(„…“) automatisch übersetzt?

#learning unit#