# Property Wrapper: Syntactic Sugar
🎁


##  Zweck
Wenn man `$message` schreibt, wird das Property `projectedValue` des PropertyWrappers verwendet.

## Beispiel

```swift
@Published
var message: String

print(message) // Print the wrapped value
$message.sink { print($0) } // Subscribe to the publisher
```

##  Hinter den Kulissen
```swift
@propertyWrapper
struct Published<Value> {
    private let subject = PassthroughSubject<Value, Never>()
    
	var wrappedValue: Value {
		didSet {
		    subject.send(wrappedValue)
		}
	}

    var projectedValue: AnyPublisher<Value, Never> {
		subject.eraseToAnyPublisher()
    }
}
```

##  Zusammenfassung

Was geschieht hinter den Kulissen, wenn man die `$`-Syntax verwendet, zum Beispiel `$message`

#learning unit# #guide