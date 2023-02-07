# Text von einer URL hohlen (lines)
🌍

## Code

```swift
let url = URL(string: "https://hws.dev/quotes.txt")!

for try await quote in url.lines {
	quotes.append(quote)
}
```

## Zusammenfassung

- Sehr einfaches Codebeispiel

#nur learning unit#