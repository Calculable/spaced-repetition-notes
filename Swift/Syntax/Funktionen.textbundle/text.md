# Funktionen
::6::

## Funktion definieren und aufrufen

### ohne eigenes Label
```swift
func greet(person: String, day: String) -> String {
    //...
}
greet(person: "Bob", day: "Tuesday")
```

### mit eigenem Label
Standartmässig gilt: Variabelname = Label
```swift
func greet(_ person: String, on day: String) -> String {
    return "Hello \(person), today is \(day)."
}
greet("John", on: "Wednesday")
```

## Parameter

### Default-Parameer

```swift
parameterWithDefault: Int = 12
```

### Varadic Parameters

```swift
func arithmeticMean(_ numbers: Double...) -> Double {/*...*/}
```

- sind als Array verfübar

### In-Out Parameters

```swift
func modifyArray(_ array: inout [Int]) {
    array[0] = 1
}

var array: [Int] = [1, 2, 3]
modifyArray(&array)

```


