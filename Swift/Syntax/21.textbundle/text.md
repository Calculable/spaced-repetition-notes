# Eigener Error-Typ 💥
::21::

```swift
enum VendingMachineError: Error { //error ist ein Protokoll
    case invalidSelection
    case insufficientFunds(coinsNeeded: Int)
    case outOfStock
}
```

## Zusammenfassung
Eigene Errors definieren
