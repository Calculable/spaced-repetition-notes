# Deque ⚫️

## Konzept
- Sind wie Queues, aber man kann Items von beiden Seiten hinzufügen und entfernen


## Implementation (gekürzt)

````swift
```swift
struct Deque<Element> {
    private var array = [Element]()
    var first: Element? { array.first }
    var last: Element? { array.last }

    mutating func prepend(_ element: Element) {
        array.insert(element, at: 0)
    }

    mutating func append(_ element: Element) {
        array.append(element)
    }

    mutating func dequeueFront() -> Element? {
        guard array.count > 0 else { return nil}
        return array.remove(at: 0)
    }

    mutating func dequeueBack() -> Element? {
        guard array.count > 0 else { return nil}
        return array.removeLast()
    }
}
````

Siehe Hacking With Swift für die vollständige Implementation 


## Zusammenfassung
- Aufbau / 4 Basisoperationen (Name unwichtig)


#nur learning unit#