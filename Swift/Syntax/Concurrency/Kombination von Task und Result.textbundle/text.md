# Kombination von Task und Result
🗒️
- Result wurde mit Swift 5.0 unwichtiger
- Bei Tasks spielt es jedoch immer noch eine grosse Rolle
- Jeder Task hat ein Result-Struct:

```swift
let inboxTask = Task { () -> [Message] in
	let url = URL(string: "https://hws.dev/inbox.json")!
    return try await URLSession.shared.decode([Message].self, from: url)
}

let inboxResult = await inboxTask.result

do {
	inbox = try inboxResult.get()
} catch {
	print(error.localizedDescription)
}
```

Beachte: Um `get` aufzurufen braucht man kein `await` mehr.

## Zusammenfassung
- Wie arbeiten Result und Task zusammen?

#learning unit#