# Compiler-Direktive für postfix member
🔀

##  Was ist ein Postfix member?

> Postfix member expressions are effectively lines of code that start with . – you’re accessing a property or a method on a type.

## Beispiel mit Compiler direktive

Neu in Swift 5.5:

```swift
Text("Welcome")
#if os(macOS)
    .font(.largeTitle)
#else
    .font(.title)
#endif
```


```swift
let selected = names
#if DEBUG
    .first
#else
    .randomElement()
#endif
```

##  Zusammenfassung

Wie kann man Compiler-Direktiven im Zusammenspielt mit Postfix Members anwenden?

#learning unit#