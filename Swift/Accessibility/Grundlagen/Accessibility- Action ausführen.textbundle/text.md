# Accessibility: Action ausführen
🦮

##  Zweck
- Der Accessibility-User kann durch Doppelklick auf ein Element eine Aktion ausführen

## UIKit
```swift
//Function called by the system when a double tap occurs on the selected wrapper.
override func accessibilityActivate() -> Bool {
	//do something
    return true
}
```

## SwiftUI
```swift
.accessibilityAction {
  // Handle Action
}
```

##  Zusammenfassung
- Swift und UIKit: Darauf reagieren wenn ein Objekt mit "Voice Over" aktiviert wird 

#learning unit#