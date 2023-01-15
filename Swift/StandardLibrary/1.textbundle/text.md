# Array modifizieren im funktionalen Stil ↩️

## Filter

```swift
let filteredNums = nums.filter { $0 <= 3 }
```

## Map

```swift
let squaredNums = nums.map { $0 * $0 }
```

## ForEach

```swift
nums.forEach { print($0) }
```

## Reduce

```swift
let sumNums = nums.reduce(0) { (sum, num) -> Int in
    sum + num
}
```

## Sort

```swift
nums.sort(by: { $0 > $1 })
```


## Um eine Kopie zu erstellen

z.B. `sorted` statt `sort`


## Zusammenfassung
- Filter
- Map
- ForEach
- Reduce
- Sort
- Was macht man, wenn man nicht die Instanz bearbeiten will sondern eine Kopie erstellen?