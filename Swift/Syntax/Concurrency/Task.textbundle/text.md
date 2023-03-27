# Task
🗒️

## Codebeispiel

Ein Task kann von einer synchronen Funktion aus gestartet werden:

```swift
let inboxTask = Task { () -> [Message] in
	let url = URL(string: "https://hws.dev/inbox.json")!
	return try await URLSession.shared.decode([Message].self, from: url)
}

inbox = try await inboxTask.value
```

=\> Der Task beginnt automatisch zu laufen

Wenn der Rückgabewert uns nicht interessiert, kann man den Task noch einfacher machen:


```swift
.task {
    Task {
        let url = URL(string: "https://hws.dev/inbox.json")!
        inbox = try await URLSession.shared.decode([Message].self, from: url)
    }

}
```


Ein Task kann wiederum Tasks erzeugen.

## Der Typ eines Tasks

- `Task<MyResultType, Error>` oder `Task<MyResultType, Never>`

Beachte: Man arbeitet jeweils mit unspezifischen Error-Typen. Das heisst, man muss im `do-catch` jeweils alle möglichen Fehler auffangen.

## Zusammenfassung
- Wie macht man eine neuen Task
	- Mit Rückgabewert
	- ohne Rückgabewert
- Welcher Typ hat ein Task?






#learning unit#