# Accessibility: System-Optionen auslesen
🦮

## Zweck

- Zum Beispiel möchte man prüfen, ob Voice Over gerade läuft oder nicht

## UIKit

### Beispiel: Is Voice Over Running?

```swift
UIAccessibility.isVoiceOverRunning
```

### Beispiel: isVideoAutoPlayEnabled?

```swift
UIAccessibility.isVideoAutoplayEnabled
```

### Beispiel: Reduce Motion

```swift
let finalState: () -> Void = {
  // Make changes for animation
}
if UIAccessibility.accessibilityReduceMotion {
  UIView.animate(
    animations: finalState
  )
} else {
  finalState()
}
```


### Liste mit allen System-Optionen

[https://developer.apple.com/documentation/uikit/uiaccessibility#3011159][1]
Siehe Abschnitt: Capabilities

## SwiftUI

### Beispiel: Differentiate without color
Beispiel: Differentiate without Color.

```swift
@Environment(\.accessibilityDifferentiateWithoutColor) var differentiateWithoutColor
```

### Beispiel: Reduce Motion

Dazu gibt es:

```swift
@Environment(\.accessibilityReduceMotion) var reduceMotion
```

Man kann es aber auch so implementieren:

```swift
func withOptionalAnimation<Result>(_ animation: Animation? = .default, _ body: () throws -> Result) rethrows -> Result {
    if UIAccessibility.isReduceMotionEnabled {
        return try body()
    } else {
        return try withAnimation(animation, body)
    }
}
```

und dann muss man nur noch schreiben:

```swift
withOptionalAnimation {
	scale *= 1.5
}
```



##  Siehe auch

Informiert werden, wenn sich Accessibility-Settings ändern: [ulysses://x-callback-url/open?id=iqZ-8Bdu8J-DzObAb\_TZow][2] (für SwiftUI ist das nicht nötig, weil dort die Infos immer aktuell sind)


## Testen
Zum Testen kann man in XCode die Environment Overrides auswählen:

![][image-1]

## Zusammenfassung

Beispiel UIKit und SwiftUI: Prüfen, ob reduceMotion aktiviert ist 

[1]:	https://developer.apple.com/documentation/uikit/uiaccessibility#3011159
[2]:	ulysses://x-callback-url/open?id=iqZ-8Bdu8J-DzObAb_TZow

[image-1]:	assets/Bildschirmfoto%202022-08-15%20um%2010.26.24.png

#learning unit#