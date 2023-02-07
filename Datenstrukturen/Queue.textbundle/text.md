# Queue
⚫️

## Konzept
- FIFO: First in, First out

## Implementation (gekürzt)

```swift
struct Queue<Element> {
    private var array = [Element]()

    func append(_ element: Element) {
        array.append(element)
    }

    func dequeue() -> Element? {
        guard array.count > 0 else { return nil }
        return array.remove(at: 0)
    }
}
```

Siehe Hacking With Swift für die vollständige Implementation 

## Priorisierung

- In einigen Implementationen kann man den Items auch eine Priorität geben
- Alternative: Mehrere Queues für unterschiedliche Prioritäten

## Zusammenfassung
- Konzept
- 2 Operationen (Name nicht so wichtig)
- Zwei Arten zur Priorisierung


#nur learning unit#