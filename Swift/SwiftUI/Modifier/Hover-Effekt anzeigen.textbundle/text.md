# Hover-Effekt anzeigen
🕴️

## Manuell

```swift
Text("Hello, World!")
    .foregroundStyle(isOverText ? .green : .red)
    .onHover { isOver in
        isOverText = isOver
    }
```

## Vordefinierter Effekt

```swift
Text("Tap me!")
    .font(.largeTitle)
    .hoverEffect(.lift)
```

![][image-1]

## Hover-Effekt testen
- Im Simulator \> i/O Menü \> Input \> Send Cursor to Device

##  Zusammenfassung
- Welche zwei Varianten gibt es?

[image-1]:	assets/2023-08-05%2008.21.02.gif

#learning unit#