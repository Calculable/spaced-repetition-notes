# Auf Szenen-Änderungen reagieren
🐇

## Codebeispiel
```swift
@Environment(\.scenePhase) var scenePhase
```

```swift
view
	.onChange(of: scenePhase) { newPhase in
		//.inactive, .active, oder .background...
	}
```

- Active: Wenn es sichtbar ist
- Inactive:  Es kann immer noch sichtbar sein aber nicht zugänglich. Zum Beispiel wenn man das App offen hat und auf das Control Center zugreift.
- Background: Nicht sichtbar für den Nutzer. Kann durch das System abgeschossen werden.


Beachte: Mit iOS 17 wird onChange im Closure keinen Parameter mehr entgegennehmen.

## Zusammenfassung
 - Zweck / Beispiel


#learning unit# #guide