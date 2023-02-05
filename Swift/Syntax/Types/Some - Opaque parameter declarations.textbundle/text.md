# Some / Opaque parameter declarations 🚗

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

##  Siehe auch

- Any / Existential Type (Unterschiede)
- Es ist performanter als „any“, weil Swift beim Kompilieren mehrere Versionen dieser Funktion erstellen kann

## Zusammenfassung
Anwendung / wie hätte man es früher gemacht?
Unterschiede zu Any?