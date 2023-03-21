# String Handling: Swift vs. Objective-C (UIKit)
💬

## Swift / SwiftUI
- Internationale Zeichen werden als individuelle Zeichen gespeichert. Das heisst: “é” ist als ein Zeichen gespeichert
- Auch Emojis zählen als einzelne Zeichen
- Ruft man `count` auf, werden Emojis oder internationale Zeichen als einzelne Zeichen gezählt

## Objective-C / UIKit

- Verwendet UTF-16
- Hier wird der „Accent“ und das „e“ separat gespeichert
- Wenn man die `count` Methode auf einem String aufruft, kommt also allenfalls nicht das erwartete Resultat zurück
- Lösung: Man verwendet `utf16.count`

## Zusammenfassung

- Was ist der Unterschied im String handling zwischen Swift/SwiftUI und Objective C / UIKit?
- Lösung für UIKit - Länge eines Strings zählen?

#learning unit#