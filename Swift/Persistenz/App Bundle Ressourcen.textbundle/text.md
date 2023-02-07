# App Bundle Ressourcen
🗂️

```swift
if let fileURL = Bundle.main.url(forResource: "some-file", withExtension: "txt") {
    if let fileContents = try? String(contentsOf: fileURL) {
    	// we loaded the file into a string!
	}
}
```

Achtung: `try?` ist evt. nicht die beste Idee

## Zusammenfassung
File vom App Bundle laden