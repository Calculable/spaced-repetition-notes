# Mehrere Protokolle als Funktionsparameter erwarten
🖇️

```swift
protocol A {
    func a()
}

protocol B {
    func b()
}

func test(example: any A & B) {
    example.a()
    example.b()
}
```

Beachte: Das `any` schreibt man nur zu Beginn der Protokolle

## Zusammenfassung
- Syntax: Funktion, die einen existential type erwartet, der zu zwei Protokollen konform ist

#learning unit#