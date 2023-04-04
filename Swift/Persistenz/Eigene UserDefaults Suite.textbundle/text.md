# Eigene UserDefaults Suite
💾

## Warum ist das sinnvoll?
- Wenn man UserDefaults zwischen mehreren Targets teilen möchte!
- Um Namenskonflikte zu verhindern, zum Beispiel mit 3rd-Party libraries!

## Code

```swift
let userDefaults = 
	UserDefaults(suiteName: "com.example.myproject")

defaults.set("Laurel", forKey: "Yanny")
```

## Zusammenfassung
- Code

#learning unit#