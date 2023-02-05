# Ordered Set 📚

## Um was geht es?

- Arrays brauchen `O(n)`, um ein bestimmtes Element zu finden
- Sets brauchen `O(1)`, um ein bestimmtes Element zu finden
- Dafür verlieren die Elemente im Set ihre Reihenfolge (Zugriff mit dem Index ist nicht möglich)

=\> Beim Ordered Set will man die Vorteile beider Strukturen kombinieren

## Nicht verwechselt

- "Ordered" heisst, dass beim Einfügen die Reihenfolge gleich bleibt, "Sorted" heisst, dass es nach einem bestimmten Kriterium sortiert wurde.

## Ziel

- Elemente mit `O(1)` finden, und trotzdem die Reihenfolge beibehalten.

## Umsetzung (gekürzt)

- Die Implementation enthält sowohl ein Array als auch ein Set:

```swift
struct OrderedSet<Element: Hashable>: Equatable {
    public private(set) var array = [Element]()
    private var set = Set<Element>()
```
\`\`\`

Siehe Hacking With Swift für die vollständige Implementation



## OrderedSet in der Standartbibliothek?

- Aktuell noch nicht in der Standartbibliothek vorhanden (ist eine offene Diskussion)
- Aus Objective-C-Zeiten gibt es das `NSOrderedSet`, das sollte aber nicht verwendet werden, weil es nicht generisch ist.

## Zusammenfassung
- Was ist ein OrderedSet (nur Theorie)



#nur learning unit#