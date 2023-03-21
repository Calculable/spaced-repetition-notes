# Auf Szenen-Änderungen reagieren
🐇

## Codebeispiel
```swift
@Environment(\.scenePhase) var scenePhase
```

```swift
view
	.onChange(of: scenePhase) { newPhase in
		//..., zum Beispiel .inactive, .active, .background...
	
	}
```


- Active: Wenn es sichtbar ist
- Inactive:  Es kann immer noch sichtbar sein aber nicht zugänglich. Zum Beispiel wenn man das App offen hat und auf das Control Center zugreift.
- Background: Nicht sichtbar für den Nutzer. Kann durch das System abgeschossen werden.

## Zusammenfassung
 - Zweck / Beispiel


#learning unit#