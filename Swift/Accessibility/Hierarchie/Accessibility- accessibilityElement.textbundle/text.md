# Accessibility: accessibilityElement
🦮 

## Zweck
- Nur wenn es True ist, wird es auch angezeigt beim navigieren mit Voice Over

## Wann wird es auf true gesetzt?
- Für Custom UIControlls
- Für die Standard-Controlls ist das bereits automatisch der Fall
- Default-Wert ist falsch, aber für Sytem-Controls ist es bereits auf True gesetzt

## UIKit
Im `init` der UIView: 

```swift
isAccessibilityElement = true
```

## SwiftUI

```swift
VStack {
    Text("Your score is")
    Text("1000")
        .font(.title)
}
.accessibilityElement(children: .ignore)
.accessibilityLabel("Your score is 1000")
```

## Siehe Unterkapitel

- Children Combine: [ulysses://x-callback-url/open?id=XOILC0iF8Q4R73riUoRKdg][1]
- Children Contain:
- Children Hidden: 

##  Zusammenfassung
- Voice Over mitteilen, dass ein Element fokussiertbar ist

[1]:	ulysses://x-callback-url/open?id=XOILC0iF8Q4R73riUoRKdg

#learning unit#