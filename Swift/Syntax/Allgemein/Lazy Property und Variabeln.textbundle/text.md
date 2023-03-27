# Lazy Property und Variabeln
🦥

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

## Beispiel 2

Bei Closures kann es sinnvoll sein, damit man auf `self` Zugreifen kann:

```swift
lazy var getAutoDetails: () -> String = {
	return "Das Modell \(self.modell) gehört \(self.besitzer)."
}
```

## Lazy Local Variable

Auch das funktioniert:

```swift
func printFibonacci(of number: Int, allowAbsolute: Bool = false) {
    lazy var result = fibonacci(of: abs(number))

	//do something with the result    
}
```

##  Zusammenfassung
- Zweck
- Codebeispiel
- Funktioniert es auch als Lokale Veriable

#learning unit#