# @discardableResult
🗑️

Folgendes gibt eine Warnung, weil man den Rückgabewert nicht ausliest:

```swift
scores.updateValue(3, forKey: "James")
```

So kann man die Warnung unterbinden:
```swift
_ = scores.updateValue(3, forKey: "James")
```

Oder man verwendet alternativ @discardableResult:

```swift
@discardableResult func updateValue(...) -> String {

}
```

## Zusammenfassung
- Zweck
- Code

#learning unit#