# Was bewirkt view.isUserInteractionEnabled = false?
🚫
##  Auswirkung
- Wenn es auf `false` gesetzt ist, dann werden keine Events mehr an die View gesendet
	- Touch Events
	- Press Events
	- Keyboard Events
	- Focus Events

## Beispiel
```swift
addTarget(self, action: #selector(touchUpInside(sender:)), for: .touchUpInside) //Wird nicht mehr aufgerufen

self.isUserInteractionEnabled = false
```





#learning unit#