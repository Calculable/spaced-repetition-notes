# SF Symbole animieren
🤹

## Beispiel

```swift
Button {
    myNumber += 1
} label: {
    Label("Click Me", systemImage: "note.text.badge.plus")
}
.symbolEffect(.bounce, value: myNumber)
```

## Resultat

![][image-1]

## Details


Man kann es auch sehr konfigurieren:

```swift
 .symbolEffect(.variableColor.reversing.cumulative, options: .repeat(3).speed(3), value: animationsRunning)
```


## Content Transition

```swift
Button {
    withAnimation {
        isChanged.toggle()
    }
} label: {
    Label("Change", systemImage: isChanged ? "calendar.circle": "person.2.wave.2.fill")
}
.contentTransition(.symbolEffect(.replace))
```

![][image-2]

## Verfügbarkeit
- Funktioniert für alle Symbole in allen Rendering Modes

##  Zusammenfassung
- Beispiel: Eine Animation kurz springen lassen (ohne Details)
- (Ohne Content Transition)

[image-1]:	assets/2023-06-17%2019.43.10.gif
[image-2]:	assets/2023-06-17%2019.51.29.gif

#learning unit# #iOS17