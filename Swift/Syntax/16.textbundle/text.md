# Extensions 👁️
::16::

## Beispiel

Häufig verwendet man Extensions um einen Typen zu einem Protokoll konform zu machen

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

## Protocol Extensions für Default Implementationen

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
Protocol Extensions
Filename