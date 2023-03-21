# .dropDestination Modifier
🎯

## Beispiel

```swift
xyView
	.dropDestination(for: Image.self) {  (images: [Image], _) in
		if let image = images.first { 
			myImage = image
			return  true
		}
		return  false
	}
```

- Kann mit allen Datentypen verwendet werden, die das `transferable`-Protokoll implementieren

## Zusammenfassung
- Wie funktioniert dropDestination? (ohne exakten Code)
- Welches Protokoll muss dafür implementiert sein?


#learning unit#