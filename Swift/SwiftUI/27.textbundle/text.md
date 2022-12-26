# APIs
::27::

## Model (Beispiel)
```swift
struct Response: Codable {
    var results: [Result]
}
```


## GET JSON

```swift
func loadData() async throws {
	let url = URL(string: "https://itunes.apple.com/search?term=taylor+swift&entity=song")! //beachte: force unwrap

	let (data, _) = try await URLSession.shared.data(from: url)

	//jetzt kann man die Daten decodieren
}
```

## POST JSON

```swift
func placeOrder() async throws {
	
	///...
	let url = URL(string: "https://reqres.in/api/cupcakes")! //beachte: force unwrap

	var request = URLRequest(url: url)
	request.setValue("application/json", forHTTPHeaderField: "Content-Type")
	request.httpMethod = "POST"

	
	let (data, _) = try await URLSession.shared.upload(for: request, from: jsonString)
}
```
