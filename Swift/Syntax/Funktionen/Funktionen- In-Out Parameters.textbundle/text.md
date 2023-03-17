# Funktionen: In-Out Parameters
📄

```swift
func modifyArray(_ array: inout [Int]) {
    array[0] = 1
}

var array: [Int] = [1, 2, 3]
modifyArray(&array)

```


#learning unit#