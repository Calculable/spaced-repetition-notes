# If mit Enum Case
🔀

##  Mit associated value
```swift
if case .success(let messages) = result {
	//...
}
```

##  Ohne associated value
```swift
if case .success = result {
	//...
}
```

##  Zusammenfassung
- Beispiel: Entspricht "result" dem enum case "succes"? (mit und ohne associated value)

#learning unit#