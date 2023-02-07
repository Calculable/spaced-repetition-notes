# FizzBuzz Test
👍

##  Anweisung
-   If the integer is evenly divisible by three, it should return “Fizz”.
-   If the integer is evenly divisible by five, it should return “Buzz”.
-   If the integer is evenly divisible by three  _and_  five, it should return “Fizz Buzz”.
-   Otherwise it should return the string form of the input number.

## Beispielcode
```swift
func fizzbuzz(number: Int) -> String {
    switch (number % 3 == 0, number % 5 == 0) {
    case (true, false):
        return "Fizz"
    case (false, true):
        return "Buzz"
    case (true, true):
        return "FizzBuzz"
    case (false, false):
        return String(number)
    }
}

print(fizzbuzz(number: 15))
```

##  Zusammenfassung
- Anweisung
- Beispielcode


#nur learning unit#