# AsyncThrowingStream / AsyncStream
🌊

## Zweck
- Implementiert`AsyncSequence`, siehe [ulysses://x-callback-url/open?id=ZjB3xhQmmUqc2O6IDfWCtw][1]
- Kann Closures oder Combine Publishers ersetzen

## Erstellen

```swift
func download(_ url: URL) -> AsyncThrowingStream<Status, Error> {
        return AsyncThrowingStream { continuation in
			//...
			continuation.yield(.downloading(10))
			//...
			continuation.yield(.downloading(50))
			//...
			continuation.yield(.downloading(100))
			//...
			continuation.yield(.finished(data))
			//...
			continuation.finish()//nicht vergessen!
			//oder alternativ bei einenm Fehler:
			//continuation.finish(throwing: error)
		}
	}
}
```


## Verwenden

Siehe  [ulysses://x-callback-url/open?id=ZjB3xhQmmUqc2O6IDfWCtw][2]

```swift
do {
    for try await status in download(...) {
        switch status {
        case .downloading(let progress):
            //...
        case .finished(let data):
            //...
        }
    }
    //hier ist der Stream geschlossen
} catch {
    //error
}
```

## Zusammenfassung
- Erstellen
- Einen Wert „veröffentlichen“
- Übertragung abschliessen
- Fehler werfen

[1]:	ulysses://x-callback-url/open?id=ZjB3xhQmmUqc2O6IDfWCtw
[2]:	ulysses://x-callback-url/open?id=ZjB3xhQmmUqc2O6IDfWCtw

#learning unit#