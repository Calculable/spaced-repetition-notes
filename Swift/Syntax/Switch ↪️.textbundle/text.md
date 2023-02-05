# Switch ↪️

## Switch mit Pattern Matching

```swift
for thing in things {
    switch thing {
    case 0 as Int:
        print("zero as an Int")
    case let someInt as Int:
        print("an integer value of \(someInt)")
    case let someDouble as Double where someDouble > 0:
        print("a positive double value of \(someDouble)")
    case is Double:
        print("some other double value that I don't want to print")
    case let (x, y) as (Double, Double):
        print("an (x, y) point at \(x), \(y)")
    default:
        print("something else")
    }
}
```
 
## Zusammenfassung
Bestimmer Wert, Typ oder Muster matchen

