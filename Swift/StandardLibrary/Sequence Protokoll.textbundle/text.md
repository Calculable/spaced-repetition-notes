# Sequence Protokoll
📚

## Zweck
- Das Sequence Protokoll erlaubt es uns, mit `for` über eine Datenstruktur zu iterieren.
- Hier gezeigt am Beispiel einer LinkedList

## Iterator zurückgeben
Als Anforderung muss man eine Funktion haben, die einen Iterator zurückgibt:

```swift
func makeIterator() -> LinkedListIterator<Element> {
    LinkedListIterator(current: start)
}
```

## Iterator implementieren
Dazu wird ein Iterator benötigt:

```swift
struct LinkedListIterator<Element>: IteratorProtocol {
    var current: LinkedListNode<Element>?

    mutating func next() -> LinkedListNode<Element>? {
        defer { current = current?.next }
        return current
    }
}
```

## Zusammenfassung
- Wozu dient das Protokoll `Sequence`)
- Was für eine Methode muss implementiert werden (nur Konzept)


#nur learning unit#