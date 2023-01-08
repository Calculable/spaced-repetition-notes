# Error werfen 💥
::21.1::

```swift
func canThrowAnError() throws -> String { //beachte: throws
    throw PrinterError.noToner
	throw VendingMachineError.insufficientFunds(coinsNeeded: 5)
}
```

## Zusammenfassung
Error werfen
