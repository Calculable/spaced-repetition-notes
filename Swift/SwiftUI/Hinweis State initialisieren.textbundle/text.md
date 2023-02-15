# Hinweis State initialisieren
🚀

## Frage

Weshalb muss man einen State im Initializer folgendermassen initialisieren:

```swift
_title = State(wrappedValue: item.itemTitle)
```

Während man im Rest vom Code folgendes schreiben kann:

self.title = item.itemTitle

## Antwort

- Mit `@State` baut man eigentlich einen Struct um seinen Wert
- Normalerweise merkt man das gar nicht, weil man mit der State-Variable genau so arbeiten kann als würde man mit dem Wert selbst arbeiten
- Beim Konstruktor ist das jedoch nicht so. Wenn wir schreiben `self.title = item.itemTitle` dann sagen wir damit eigentlich aus, dass wir den gewrappten Title-Wert innerhalb des State-Structs anpassen möchten. Zum Zeitpunkt des initializers gibt es aber noch gar keinen State Struct!

## Hinweis

- Das Initialisieren von State auf diese Weise ist nicht empfohlen. Manchmal ist es aber die einfachste Lösung (zum Beispiel bei einer Edit-View)

## Zusammenfassung
- Weshalb müssen State-Variabeln im Initializer speziell initialisiert werden?


#nur learning unit#