# Extensions 👁️
::16::

## Beispiel
```swift
extension Int: ExampleProtocol {
    var simpleDescription: String {
        return "The number \(self)"
    }
    mutating func adjust() {
        self += 42
    }
}
print(7.simpleDescription)
```

## Häufiger Anwendungsfall: Protocol Extensions

```swift
extension SomeType: SomeProtocol, AnotherProtocol {
    //...
}
```

## Protocol Extensions

- Beinhalten Default-Implementierungen für ein Protokoll

```swift
protocol Fighter {
	func eject()
}

extension Fighter {
	func eject() {
		print("Bye!")
	}
}
```

##  Filename

z.B. `Bundle+Ext.swift`

## Zusammenfassung
Beispiel
Protokolle implementieren
Protocol Extensions
Filename