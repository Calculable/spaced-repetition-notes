# Funktionen: In-Out Parameters
📄

> Function parameters are constants by default. Trying to change the value of a function parameter from within the body of that function results in a compile-time error. 


```swift
func modifyArray(_ array: inout [Int]) {
    array[0] = 1
}

var array: [Int] = [1, 2, 3]
modifyArray(&array)

```


#learning unit#