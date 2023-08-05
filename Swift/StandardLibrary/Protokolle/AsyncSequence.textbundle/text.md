# AsyncSequence
🔃
- Ist ein Protokoll
- Erlaubt asynchrones Iterieren
- Als Implementation verwendet man häufig `AsyncThrowingStream / AsyncStream` (siehe [ulysses://x-callback-url/open?id=U0FKcnR7R\_WCec8xqOUYCQ][1])

```swift
for await count in myAsyncSequence {
    print(count)
}
```

- Es gibt auch viele Methoden ähnlich wie bei `Sequence`, zum Beispiel `map`, `filter`, `contains`, …

```swift
myAsyncSequence.filter({ $0 % 2 == 0 })
```

```swift
await myAsyncSequencecontains(3)
```


## Zusammenfassung
- Durch eine AsyncSequence iterieren
- Was sind zwei Implementationen des Protokolls?

[1]:	ulysses://x-callback-url/open?id=U0FKcnR7R_WCec8xqOUYCQ

#learning unit#