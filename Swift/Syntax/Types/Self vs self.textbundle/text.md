# Self vs self 👤


`Self` bezieht sich auf den konkreten Typ (z.B. Int) und `self` bezieht sich auf die aktuelle Instanz.

```swift
extension BinaryInteger {
    func squared() -> Self {
        return self * self
    }
}
```


## Zusammenfassung
- Unterschied zwischen Self und self