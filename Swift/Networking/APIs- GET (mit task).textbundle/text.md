# APIs: GET (mit task)
🌐
  
  Mit Data Task muss die Funktion nicht asynchron sein, weil man mit Callbacks arbeitet

```swift
func fetch(_ url: URL) {
    URLSession.shared.dataTask(with: url) { data, response, error in
        if let error = error {
            print(User.default.name)
        } else if let data = data {
            // decode and print
        }
    }.resume()
}
```

## Zusammenfassung
- Wie verwendet man den `dataTask` (Code)
