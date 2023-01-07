# Lazy Variable 🦥

## Zweck
> These variables are created using a function you specify only when that variable is first requested. If it's never requested, the function is never run, so it does help save processing time.

## Beispiel
```swift
struct Person {
    var age = 16

    lazy var fibonacciOfAge: Int = {
        fibonacci(of: self.age)
    }()
}
```

Lazy Let existiert nicht.

##  Zusammenfassung
- Zweck
- Codebeispiel