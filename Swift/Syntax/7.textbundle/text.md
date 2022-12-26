# Closures
::7::

## Syntax

### Beispiel 1
```swift
numbers.map({ (number: Int) -> Int in
    let result = 3 * number
    return result
})
```

### Beispiel 2

```swift
let mappedNumbers = numbers.map({ number in 3 * number })
```

### Beispiel 3

```swift
numbers.map({ 2*$0});
```

### Beispiel 4 (trailing closure)
```swift
numbers.sorted { $0 > $1 }
```

## Zugriff

> The code in a closure has access to things like variables and functions that were available in the scope where the closure was created, even if the closure is in a different scope when it’s executed

