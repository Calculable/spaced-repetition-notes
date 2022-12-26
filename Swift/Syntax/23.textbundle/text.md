# Do-Catch
::23::

```swift
do {
    //try ...
} catch PrinterError.onFire {
    //...
} catch let printerError as PrinterError {
    //...
} catch {
    print(error)
}
```

Man kann mehrere Catch mit Komma trennen:

```swift
catch VendingMachineError.invalidSelection, VendingMachineError.insufficientFunds {
        //...
    }
```

Wenn man einen Parameter hat innerhalb des Fehlers:

```swift
catch VendingMachineError.insufficientFunds(let coinsNeeded) {
    //...
}
```
