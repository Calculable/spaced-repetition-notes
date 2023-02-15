# DropDestination
🎯

## Beispiel

```swift
xyView
	.dropDestination(payloadType: Image.self) {  (images: [Image], _) in
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


#nur learning unit#