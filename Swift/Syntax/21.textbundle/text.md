# Eigener Error-Typ 💥
::21::

##  Eigene Errors definieren

```swift
enum VendingMachineError: Error { //error ist ein Protokoll
    case invalidSelection
    case insufficientFunds(coinsNeeded: Int)
    case outOfStock
}
```

## Error werfen

```swift
func canThrowAnError() throws -> String { //beachte: throws
    throw PrinterError.noToner
	throw VendingMachineError.insufficientFunds(coinsNeeded: 5)
}
```

## Zusammenfassung
Eigene Errors definieren
Error werfen