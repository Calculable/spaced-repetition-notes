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


## Zusammenfassung
 - Zweck / Beispiel


#nur learning unit# #learning unit#