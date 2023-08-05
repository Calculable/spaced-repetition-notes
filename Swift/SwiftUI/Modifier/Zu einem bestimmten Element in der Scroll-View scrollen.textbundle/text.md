# Zu einem bestimmten Element in der Scroll-View scrollen
📜

```swift
ScrollViewReader { proxy in
	VStack {
		Button("Jump") {
			withAnimation {
				proxy.scrollTo(10)
				//oder für mehr Konfiguration:
				proxy.scrollTo(10, anchor: .top)
			}
		}

		List(0..<50, id: \.self) { i in
			Text("\(i)")
			.id(i)
		}
	}
}
```

## Zusammenfassung
- (Primär Konzept, nicht den exakten Code)

#learning unit#