# .focused Modifier

- Seit iOS 15

Damit kann man zum Beispiel die Tastatur ausblenden, wenn man sie nicht mehr benötigt:

```swift
@FocusState private var numberIsFocused: Bool

TextField("Enter your phone number", text: $phoneNumber)
	.focused($numberIsFocused)
```


Hinweis: In UIKit macht man dies mit `resignFirstResponder()`

Details (zum Beispiel Fokus mit mehreren Feldern managen - siehe hier: 
[https://www.hackingwithswift.com/plus/hacking-with-swift-live-2021/swipe-actions-markdown-and-focus][1])

[1]:	https://www.hackingwithswift.com/plus/hacking-with-swift-live-2021/swipe-actions-markdown-and-focus

#learning unit#