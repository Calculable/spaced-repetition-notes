# Accessibility 🦮
::21::

## Beschreiben, was auf einem Bild ist

```swift
.accessibilityLabel(...)
```
Das soll ein Kurzer Text sein, der direkt vorgelesen wird.  Ansonsten wird einfach der Filename vorgelesen. (z.B: „Delete“)

```swift
.accessibilityHint(...)
```
Der Hint wird nach einem kurzen Delay vorgelesen und kann ausführlicher sein („Delete Email from Mailbox“)

## Beschreiben, das etwas ein Button ist
```swift
.accessibilityAddTraits(.isButton)
.accessibilityRemoveTraits(.isImage)
```

Es gibt noch weitere, zum Beispiel: `.isSelected`

## Image als Decorative kennzeichnen

```swift
Image(decorative: "character")
```

## Views komplett verstecken
```swift
Image(decorative: "character")
    .accessibilityHidden(true)
```

##  Grouping

```swift
VStack {
    Text("Your score is")
    Text("1000")
        .font(.title)
}
.accessibilityElement(children: .combine)
```

```swift
VStack {
    Text("Your score is")
    Text("1000")
        .font(.title)
}
.accessibilityElement(children: .ignore) //ignore ist der default parameter
.accessibilityLabel("Your score is 1000")
```

## Accessibility Options

Beispiel: Differentiate without Color.


```swift
@Environment(\.accessibilityDifferentiateWithoutColor) var differentiateWithoutColor
```

## Zusammenfassung
- Beschreiben was auf einem Bild ist (2 Möglichkeiten)
- Im ScreenReader ausblenden
- Kennzeichnen, dass etwas ein Button ist
- Bild als derokartiv kennzeichnen
- Kinder gruppieren
- Kinder ignorieren
- Wichtige Environment properties auslesen: z.B. differenciateWithoutColor