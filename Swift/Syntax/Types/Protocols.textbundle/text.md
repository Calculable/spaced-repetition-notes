# Protocols
📜

```swift
protocol ExampleProtocol {
	init(someParameter: Int) //Initializer Requirement
    var simpleDescription: String { get }
    mutating func adjust()
	static var someTypeProperty: Int { get set } //beachte: nicht "class"
}
```

## Zusammenfassung
Initializer
Property mit Setter und Getter
Funktionen (z.B. Mutating)