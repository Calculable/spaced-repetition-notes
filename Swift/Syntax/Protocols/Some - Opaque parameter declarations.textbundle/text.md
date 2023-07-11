# Some / Opaque parameter declarations
🚗

## Einordnung

- Gibt es erst seit Swift 5.7

## Beispiel

```swift
func isSorted(array: [some Comparable]) -> Bool {
    array == array.sorted()
}
```

Früher hätte man es so schreiben müssen:

```swift
func isSortedOld<T: Comparable>(array: [T]) -> Bool {
    array == array.sorted()
}
```


##  Weiteres Beispiel

Mit `some` muss man immer den gleichen Typ haben

```swift
let vehicles: [some Vehicle] = [ 
    Car(),
    Car(),
    Car(),
]

```

```swift
var myCar: some Vehicle = Car()
myCar = Bus() // 🔴 Compile error
```

Mit `any` kann sich die Implementation jedoch zur Laufzeit verändern

## Zusammenfassung
- Zweck
- Wie hätte man es früher gemacht (some parameter declaration sind eigentlich nur syntactic sugar)


#learning unit#