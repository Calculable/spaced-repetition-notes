# Funktionen: In-Out Parameters
📄

- Siehe eigener Eintrag

```swift
func modifyArray(_ array: inout [Int]) {
    array[0] = 1
}

var array: [Int] = [1, 2, 3]
modifyArray(&array)

```
