# Collection Protokolle
🥞

| Protokoll                    | Eigenschaft                     |
| ---------------------------- | ------------------------------- |
| Sequence 🔁                  | Iterierbar (mind. 1x)           |
| Collection 👆                | Iterierbar, Index-Access        |
| RandomAccessCollection 🚀    | Index-Access in O(1)            |
| MutableCollection ✍️         | Elemente ändern                 |
| RangeReplacableCollection 📥 | Elemente einfügen und entfernen |


##  Zusammenfassung
- Haupteigenschaften von:
- RandomAccessCollection
- Sequence
- Collection
- MutableCollection
- RangeReplacableCollection


## Details

### Sequence

#### Zweck
- Erlaubt es, durch die Collection zu iterieren.
- Es gibt keine Garantie darüber, dass man mehrfach iterieren kann
- Um das Protokoll zu implementieren, muss man einen Iterator zurückgeben können.

#### Iterator zurückgeben
Als Anforderung muss man eine Funktion haben, die einen Iterator zurückgibt:

```swift
func makeIterator() -> LinkedListIterator<Element> {
    LinkedListIterator(current: start)
}
```

#### Iterator implementieren
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

### Collection


- Man kann eine Collection mehrfach iterieren
- Dabei hat man die Garantie, dass das Iterieren nicht-destruktiv ist
- Ausserdem kann man mit einem Index oder mit einem Slice auf die Elemente zugreifen (lesend)


### RandomAccessCollection
- Ein Protokoll, welches besagt, dass man über ein Subscript mit Index auf die Elemente zugreifen kann.
- Wird zum Beispiel von Array implementiert
- Es ermöglicht auch Dinge wie `for`-Loops oder die `map`-Funktion, `allSatisfy` etc.



### MutableCollection

- Hier kann man die einzelnen Elemente in der Collection verändern (Mit Index- oder Slice-Zugriff)
- Achtung: Man kann einzelne Elemente verändern, aber nicht die Länge des Arrays. Dazu braucht man eine `RangeReplacableCollection`.

### RangeReplacableCollection
- Collection, in der man Elemente einfügen oder entfernen kann.

#learning unit#