# Accessibility: Accessibility Traits
🦮 


##  Wozu werden Traits benötigt?
Das Trait wird nach dem Label vorgelesen. Ausserdem werden Traits auch für andere Accessibility-Funktionen gebraucht: Zum Beispiel kann man mit dem Rotor direkt "Header"-Elemente anspringen. Oder mit dem Trait "isButton" weiss das System dass das Element auf Doppelklick reagiert

## UIKit

###  Einzelner Trait setzen

(Ersetzt bereits vorhandene Trait)
```swift
myView.accessibilityTraits = .button
```

### Einen Trait hinzufügen / enfernen

Es handelt sich um eine Bitmask/Option Set

```swift
myView.accessibilityTraits.insert(.header)
myView.accessibilityTraits.remove(.header)
```


## SwiftUI

```swift
.accessibilityAddTraits(.isButton)
.accessibilityRemoveTraits(.isImage)
```

Es gibt noch weitere, zum Beispiel: `.isSelected`

##  Übersicht der verfügbaren Traits

### Button
- Element kann über Doppelklick aktiviert werden

### isToggle
Wird so vorgelesen:
"Switch Button, Double Tab to toggle setting"

### Header
- Damit kann man über den Rotor direkt die Header-Elemente anspringen

![][image-1]

###  Summary Element
- Enthält eine Zusammenfassung von wichtigen Informationen
- Wird direkt vorgelesen wenn der Screen angezeigt wird
- Beim Apple Wetter-App ist das zum Beispiel die Temperatur

###  Adjustable
- Für Sliders und Counters etc. So kann der Wert mit Gesten aktualisiert werden

### Link

Link zu einer Webseite


###  Search Field

Der User wird informiert dass sich der Screen verändert während man tippt

### Static Text

Ein Text der sich nicht verändert

### Tabbar

Wenn man eine Custom Tabbar hat

### Not Enabled

(Keine Interaktion möglich)


###  Causes Page Turn
(Siehe Dokumentation)$

z.B. bei der Books-App: Dort wird die Seite umgeblätter sobald aller Text auf einer Seite gelesen wurde


### PlaysSound

(Klar)

###  Starts Media Session
- Zum Beispiel wenn man eine Audio-Aufnahme startet
- Damit verhindert man, dass Voice Over die Media Session unterbricht
- Voice Over wird also stummgeschalten


Use this trait to silence the audio output of an assistive app, such as VoiceOver, during a media session that you don't want to interrupt. For example, you might use this trait to silence VoiceOver speech while the user is recording audio.

###  Allows Direction Interaction

Damit sagt man dem Sytsem dass die View direkt auf Berührungen reagieren soll und nicht über die "normale Voice Over Bedienung". Das ist oft sinnvoll für Custom Sliders oder Flächen auf denen man zeichnen kann.

Siehe [ulysses://x-callback-url/open?id=vzPVHp5jT5tbcvhs94BlYA][1]


### Alle Traits
Siehe [https://developer.apple.com/documentation/uikit/uiaccessibilitytraits][2]

## Zusammenfassung
- UIKit und SwiftUI: einzelner trait hinzufügen

[1]:	ulysses://x-callback-url/open?id=vzPVHp5jT5tbcvhs94BlYA
[2]:	https://developer.apple.com/documentation/uikit/uiaccessibilitytraits

[image-1]:	assets/Bildschirmfoto%202024-01-30%20um%2021.25.51.jpeg

#learning unit#