# Accessibility: Beschreiben, was auf einem Bild ist
🦮

## Beschreiben, was auf einem Bild ist

```swift
.accessibilityLabel(...)
```
Das soll ein Kurzer Text sein, der direkt vorgelesen wird.  Ansonsten wird einfach der Filename vorgelesen. (z.B: „Delete“)

```swift
.accessibilityHint(...)
```
Der Hint wird nach einem kurzen Delay vorgelesen und kann ausführlicher sein („Delete Email from Mailbox“)

## Unterscheidung AccessibilityLabel und AccessibilityValue

> Beachte: Der Value ist zum Beispiel für einen Wert einer Progressbar während das Label für den Titel der Progressbar steht

## Zusammenfassung
- Beschreiben was auf einem Bild ist (2 Möglichkeiten)

#learning unit#