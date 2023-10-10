# Tasks abbrechen
❌

##  Code

Mark for Cancellation:
```swift
task.cancel()
```


##  Cooperative Cancellation: Der Task kann selbst entscheiden, wie er auf den Abbruch reagiert

- Wenn man nicht explizit den Task anpasst, dann wird der Abbruch einfach ignoriert
- Das heisst innerhalb des Tasks muss man explizit prüfen, ob es abgebrochen wurde und darauf reagieren
- Wenn man zum Beispiel in einem Loop Primzahlen überprüft, kann man entweder ein leeres Array zurückgeben, oder die bereits gefundenen Primzahlen:

## Variante 1: Check
```swift
for check in 1...number {   
	if number.isMultiple(of: check) {
		result.append(check) 
		await Task.yield()
    }

	if Task.isCancelled {
		return result
	}
}
```

So kann man einen Fehler werfen, wenn eine Cancellation vorliegt:

## Variante 2: Throw on Cancel
```swift
Thread.checkCancellation() //Throws error if cancelled 
```

## Variante 3: Cancellation Handler


```swift
 await withTaskCancellationHandler(operation: { [weak self] in
	await myTask
}, onCancel: { [weak self] in
	//do something
})
```

Wird auch dann aufgerufen, wenn der Task gerade nicht aktiv am Laufen ist



##  Vorsicht bei Verwendung APIs

- APIs werden natürlich ebenfalls prüfen, ob eine Cancellation vorliegt
- So wirft zum Beispiel URLSession einen Error wenn eine Cancellation geschehen ist


## SwiftUI

- Bei der Verwendung von SwiftUI’s task() modifier wird ein Task abgebrochen, wenn die View nicht mehr angezeigt wird


> If you have started a task using SwiftUI’s task() modifier, that task will automatically be cancelled when the view disappears.

> So, we have implicit cancellation checks when APIs check for cancellation automatically, and explicit cancellation checks when we read isCancelled or manually.

##  Zusammenfassung
- Wie bricht man einen Task ab?
- Was bedeutet Cooperative Cancellation? Auf welche drei Arten kann man es implementieren
- Was gilt für den SwiftUI task() modifier?

#learning unit#