# Multiple Constrained Methods ✋

## Verhalten
- Wenn es mehrere gleiche Methoden gibt, dann wählt Swift jeweils diejenige Methode aus, die am Stärksten "Constrained" ist.

## Repetition: Beispiel für eine Constrained Method

```swift
extension Queue where Element: Prioritized {
    mutating func dequeue() -> Element? {}
}
```

## Zusammenfassung
- Wie entscheidet sich der Compiler für eine Constrained Method bei mehreren gleichnamigen Constrained Methods?


#nur learning unit#