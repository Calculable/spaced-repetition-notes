# Kombination von Task und Result
🗒️
- Result wurde mit Swift 5.0 unwichtiger
- Bei Tasks spielt es jedoch immer noch eine grosse Rolle
- Jeder Task hat ein Result-Struct:

```swift
let articleTask = Task { () -> [Article] in
	let url = URL(string: "https://myservice.ch/news.json")!
    return try await URLSession.shared.decode([Article].self, from: url)
}

let articlesResult = await articleTask.result

do {
	articles = try articlesResult.get()
} catch {
	print(error.localizedDescription)
}
```

Beachte: Um `get` aufzurufen braucht man kein `await` mehr.

## Zusammenfassung
- Wie arbeiten Result und Task zusammen?

#learning unit#