# Pattern: Mocks Injecten
💉

## Protokoll

```swift
protocol APIProtocol {
	func getEmoji()
}
```

## View
```swift
struct ContentView<C: APIProtocol>: View {
    @State private var emoji = "🫥"

    var body: some View {
        Text(emoji)
    }

    let client: C

    init(client: C) {
        self.client = client
    }

	//Since the init function does not use any parameter we use „C == RealClient“ to tell the compiler that if the init function without parameter is used, the return type would be of ContentView<RealClient>?
    init() where C == RealClient {
        self.client = RealClient()
    }

    func updateEmoji()  {
        emoji = client.getEmoji
    }
}

```

## RealClient

```swift
struct RealClient: APIProtocol {
    func getEmoji() -> String {
        return "😃"
    }
}
```

Injection: 

```swift
//Zum Beispiel für Preview
ContentView()
```

## Mock

```swift
struct MockClient: APIProtocol {
    func getEmoji() -> String {
        return "🤖"
    }
}
```

Injection: 

```swift
//Zum Beispiel für Preview
ContentView(client: MockClient())
```

## Zusammenfassung
- Wie kann man eine View entsprechend Generische machen, so dass man einen Protocol-Mock injecten kann?

#learning unit#