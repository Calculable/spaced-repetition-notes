# Parameter 📄
::6.1::


## Default-Parameer

```swift
parameterWithDefault: Int = 12
```

## Varadic Parameters

```swift
func arithmeticMean(_ numbers: Double...) -> Double {/*...*/}
```

- sind als Array verfübar

## In-Out Parameters

- Siehe eigener Eintrag

```swift
func modifyArray(_ array: inout [Int]) {
    array[0] = 1
}

var array: [Int] = [1, 2, 3]
modifyArray(&array)

```


## Zusammenfassung
- Default-Parameter
- Varadic Parameter
- In-Out Parameter