# Rethrows ⚽️

> The  `rethrows`  keyword is used when you write a function (let’s call it A) that accepts a throwing function as a parameter (let’s call it B). If function B throws errors, then the function A becomes a throwing function too, but if function B doesn’t throw errors then neither does function A.


```swift
func authenticateUser(method: (String) throws -> Bool) rethrows {
    try method("twostraws")
    print("Success!")
}
```


## Zusammenfassung
- Was ist Rethrows und wie wird es angewendet?