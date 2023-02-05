# Linked List 🖇️

## Unterschied zum Array
- Array sind sehr schnell im **Random Access**
	- Allerdings müssen beim Löschen viele Elemente umkopiert werden

- Linked Lists sind sehr langsam im **Random Access**
	- Weil man von Element zu Element springen muss
	- Dafür sind sie sehr schnell beim Löschen, weil man nicht alles umkopieren muss

## Implementation (gekürzt)

```swift
final class LinkedList<Element> {
    var start: LinkedListNode<Element>?
}
```

```swift
final class LinkedListNode<Element> {
    var value: Element
    var next: LinkedListNode?

    init(value: Element) {
        self.value = value
        self.next = next
    }
}
```

Siehe Hacking With Swift für die vollständige Implementation


## Warum ist es eine Klasse statt ein Struct

- Weil ansonsten das Struct sich selbst beinhalten würde (somit wäre es unendlich gross)

## Double Linked List

- Damit kann man in beide Richtungen navigieren.


## Zusammenfassung
- Vorteil im Vergleich zu Array
- Nachteil im Vergleich zu Array
- Warum eine Klasse
\- 


#nur learning unit#