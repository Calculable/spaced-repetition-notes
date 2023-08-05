# Class-Only Protocol


> A class-only protocol is marked by its inheritance from AnyObject

```swift
protocol DiceGameDelegate: AnyObject {}
```

=\> Das wird sehr häufig von Delegates eingesetzt, weil man diese  mit `weak` referenzieren will


##  Zusammenfassung
- Wie macht man ein Protokoll, das nur von Klassen implementiert werden kann?
- Wo ist das sinnvoll?

#learning unit#