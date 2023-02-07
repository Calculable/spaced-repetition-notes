# APIs: GET (asynchron)
🌐

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


## Zusammenfassung
- Api-Zugrif: Die Funktion ist… ?
- Protokoll für die Modelklassen
- URL erzeugen
- Daten empfangen
