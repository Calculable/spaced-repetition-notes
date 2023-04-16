# Learning: Task Denkfehler
🧠

## Dieser Code hat das UI blockiert

```swift
Button("Run with Task (blocks UI)") { 
    Task {
		countPrimeNumbersInRange(range: 1...numberOfChecks)   
    }
}
```

## Warum ist das so?

Ich habe innerhalb des Tasks gar keine Async-Funktion aufgerufen. 

Richtige wäre es so:

```swift
await countPrimeNumbersInRange(range: 1...numberOfChecks)
```

## Zusammenfassung
- Warum kann das UI selbst dann blockieren, wenn man eigentlich einen Task verwendet?

#learning unit#