# Enums
🪸

## Mit Typextension
```swift
enum Rank: Int {
    case ace = 1 //default: 0
    case two, three, four, five

    func simpleDescription() -> String {
        switch self {
	        case .ace:
	            return "ace"
	        default:
	            return String(self.rawValue)
        }
    }
}
let ace = Rank.ace
let aceRawValue = ace.rawValue
```

## Mit Associated Value

```swift
enum ServerResponse {
    case result(String, String)
    case failure(String)
}
```

Kann dann zum Beispiel mit Pattern Matching verwendet werden:
```swift
switch success {
case let .result(sunrise, _):
    print("Sunrise is at \(sunrise)")
case let .failure(message):
    print("Failure...  \(message)")
}
```

## Zusammenfassung
Mit Typ-Extension
Mit Associated Value