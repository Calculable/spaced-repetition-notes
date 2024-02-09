#  AsyncStream
🌊

## Zweck
- Implementiert`AsyncSequence`, siehe [ulysses://x-callback-url/open?id=ZjB3xhQmmUqc2O6IDfWCtw][1]
- Kann Closures oder Combine Publishers ersetzen

## Erstellen

```swift
func getStream() -> AsyncStream<Int> {
    let stream = AsyncStream { stream in
        stream.yield(1)
        stream.yield(2)
        stream.yield(3)
        stream.finish()
    }

    return stream
}
```

## (Implementationsdetails verstecken)

Man könnte es auch so zurückgeben:

```swift
func getStream() -> some AsyncSequence where Element == Int
```

## Verwenden

```swift
for await x in getStream() {
    print(x)
}

print("finished")
```

## Siehe auch
- AsyncThrowingStream: [ulysses://x-callback-url/open?id=DAydJmtlpV5TyUmmTO1GXw][2]

## Zusammenfassung
- Erstellen
- Einen Wert „veröffentlichen“
- Übertragung abschliessen

[1]:	ulysses://x-callback-url/open?id=ZjB3xhQmmUqc2O6IDfWCtw
[2]:	ulysses://x-callback-url/open?id=DAydJmtlpV5TyUmmTO1GXw

#learning unit#