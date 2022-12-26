# Protocols
::14::

```swift
protocol ExampleProtocol {
	init(someParameter: Int) //Initializer Requirement
    var simpleDescription: String { get }
    mutating func adjust()
	static var someTypeProperty: Int { get set } //beachte: nicht "class"
}
```
