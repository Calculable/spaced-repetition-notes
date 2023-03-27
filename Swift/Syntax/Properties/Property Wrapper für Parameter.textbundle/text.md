# Property Wrapper für Parameter
📦

## Beispiel

Neu in Swift 5.5

- Der Wert wird transformiert, bevor man ihn in der Funktion verwendet


```swift
func setScore2(@Clamped(range: 0...100) to score: Int) {
    print("Setting score to \(score)")
}

setScore2(to: 50)
setScore2(to: -50)
setScore2(to: 500)
```


## Zusammenfassung
- Wie kann man einen Property-Wrapper für einen Funktionsparameter anwenden?

#learning unit#