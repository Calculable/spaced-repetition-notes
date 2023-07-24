# Combine und Foundation
🔀

##  Networking

```swift
URLSession.shared.dataTaskPublisher(for: URL(string: "https://www.avanderlee.com/feed/")!)
    .map { $0.data }
    .decode(type: DecodableExample.self, decoder: JSONDecoder())
```

## Notifications

```swift
NotificationCenter.default.publisher(
	for: .NSSystemClockDidChange
)
```

##  Timer

```swift
let publisher = Timer
	.publish(every: 1.0, on: .main, in: .common)
	.autoconnect()
```

##  Zusammenfassung
(ohne Code): An welchen Orte in Foundation wird Combine eingesetzt?

#learning unit#