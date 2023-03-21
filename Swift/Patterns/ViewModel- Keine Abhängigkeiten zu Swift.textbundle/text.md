# ViewModel: Keine Abhängigkeiten zu Swift
✂️

## Missverständnis

- Das ViewModel muss NICHT SÄMTLICHE Funktionen und Properties aus einer View entfernen, sondern nur diejenigen, die nicht direkt mit der Darstellung zu tun haben.

## Hinweis

ViewModels sollen SwiftUI nicht importieren!

## Beispiele: Was kann in der View bleiben?

### withAnimation

=\> Sollte man nicht im ViewModel machen. Einerseits konzeptionell und andererseits weil man dafür SwiftUI importieren muss

Stattdessen macht man eine Funktion in der View (das ist erlaubt), welche `withAnimation` enthält, und die Funktion im ViewModel aufruft.

### Properties wie `showEditSheet`

- Hier geht es ja nur um die Darstellung


## Zusammenfassung
- Was war mein Missverständnis
- Was kann in der View bleiben?

#learning unit#