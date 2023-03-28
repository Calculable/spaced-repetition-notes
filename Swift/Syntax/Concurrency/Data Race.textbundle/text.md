# Data Race
🏇

##  Definition
- Ein Bug: Wenn zwei Threads auf eine geteilte Ressource zugreifen und dies zu unvorhersehbarem oder inkonsistenten Verhalten führt.

##  Beispiel

```swift
class BankAccount {
    var balance: Decimal

    init(initialBalance: Decimal) {
        balance = initialBalance
    }

    func deposit(amount: Decimal) {
        balance = balance + amount
    }

    func transfer(amount: Decimal, to other: BankAccount) {
        guard balance > amount else { return }
        balance = balance - amount
        other.deposit(amount: amount)
    }
}
```

- Wenn zwei Threads gleichzeitig Geld abheben kann es sein, dass die Balance negativ wird:
	- Weil beide Threads am „Guard“ Statement vorbeikommen, weil die Balance noch nicht angepasst ist

## Wie kann man dieses Problem verhindern
- Manuell, zum Beispiel mit Locks
- Einfachste Lösung: Actor verwenden

##  Zusammenfassung
- Definition
- (allenfalls Beispiel)
- Lösung


#learning unit#