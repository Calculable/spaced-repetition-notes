# APIs: POST 🌐

## Model (Beispiel)
```swift
struct Response: Codable {
    var results: [Result]
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

## Zusammenfassung
- Api-Zugrif: Die Funktion ist… ?
- Protokoll für die Modelklassen
- Daten hochladen