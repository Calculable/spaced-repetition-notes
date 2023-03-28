# Einen Teil des Actors nonisolated machen
🗃️

## Beispiel

```swift
import CryptoKit
import Foundation

actor Example {
    let myConstant: String
    var myVariable: String

    init(myConstant: String, myVariable: String) {
        self.myConstant = myConstant
        self.myVariable = myVariable
    }

    nonisolated func myConstantHash() -> String {
        let data = Data(myConstant.utf8)
        let hash = SHA256.hash(data: data)
        return hash.compactMap { String(format: "%02x", $0) }.joined()
    }
}
```

=\> So kann `myConstantHash` ohne `await` aufgerufen werden.

## Wo ist das Möglich?

- Bei Funktionen und Computed Properties
	- Aber nur, wenn in der Funktion oder dem Computed Property ebenfalls nur auf non-isolated properties und Methods zugegriffen wird.

## Wo ist es nicht möglich
- Bei Konstanten Properties
	- Bei Konstanten ist es nicht möglich, weil man auf diese sowieso ohne `await` zugreifen kann
	- Bei Variabeln ist es nicht möglich, weil das keinen Sinn ergeben würde

## Anwendungsfall

- Besonders hilfreich wenn man zum Beispiel zu Hashable oder Codable konform sein muss (diese Funktionen müssen ja dann ausserhalb des Actors aufgerufen werden)


##  Zusammenfassung
- Wie macht man einen Teil des Actors unisolated?
- Wo ist es möglich und wo nicht?


#learning unit#