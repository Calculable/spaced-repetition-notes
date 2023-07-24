# Asynchrone Funktion aufrufen
⏰
 
## ….innerhalb einer asynchronen Funktion

```swift
await loadData()
```

## …innerhalb einer synchronen Funktion

```swift
Task {
	do {
		 self.images = try await fetchImages()
    } catch {
    	// .. handle error
    }
}
```

Der folgende Code gibt zum Beispiel zuerst 1 und erst dann 2 aus:

```swift
Task {
	await printTwo()
}
print(1)
```

Hinweis: Das `.init` muss man nicht unbedingt schreiben

## …wenn eine View angezeigt wird

Add this modifier to the List now:

```swift
.task {
    await loadData()
}
```

- Das ist die asynchrone Version von `onAppear()`


## Zusammenfassung
- Aufruf: von async Code, von sync code, von SwiftUI View


#learning unit#