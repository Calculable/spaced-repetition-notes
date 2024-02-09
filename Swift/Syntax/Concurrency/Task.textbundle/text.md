# Task
🗒️

## Codebeispiel

Ein Task kann von einer synchronen Funktion aus gestartet werden:

```swift
let articleTask = Task { () -> [Article] in
	let url = URL(string: "https://myservice.ch/news.json")!
	return try await URLSession.shared.decode([Article].self, from: url)
}

articles = try await articleTask.value
```

=\> Der Task beginnt automatisch zu laufen

Wenn der Rückgabewert uns nicht interessiert, kann man den Task noch einfacher machen:


```swift
Task {
    let url = URL(string: "https://myservice.ch/news.json")!
    inbox = try await URLSession.shared.decode([Article].self, from: url)
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