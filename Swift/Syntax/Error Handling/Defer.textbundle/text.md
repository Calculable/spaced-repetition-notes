# Defer
🛏️

- Wird immer ausgeführt direkt vor dem Return 
- Auch wenn ein Error auftreten sollte.
- Vorteil: Man kann setup und cleanup-code nacheinander schreiben

```swift
func fridgeContains(_ food: String) -> Bool {
    fridgeIsOpen = true
    defer {
        fridgeIsOpen = false
    }

    let result = fridgeContent.contains(food)
    return result
}
```

## Mehrere Deferred Actions
> Deferred actions are executed in the reverse of the order that they’re written in your source code. That is, the code in the first defer statement executes last, the code in the second defer statement executes second to last, and so on. The last defer statement in source code order executes first.

##  Zusammenfassung
- Syntax und Zweck

#learning unit#