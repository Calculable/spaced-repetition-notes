# Map
🗺️
## Beispiel

```swift
let result1 = numbers1.map { element in
    Double(element)
}
```

## Wo ist `map` sonst noch unterstützt?

- **Optional**: map will extract the value wrapped inside, transform it using a function we specify, then place it back into another `Optional` - siehe separates Kapitel
- **Result**: if saved data was loaded successfully then transform it, otherwise do nothing. (Alternativ gibt es auch `mapError`)

## Functors (nicht auswändig)

> any data type that can be mapped over using `map()` is called a _functor_, as long it abides by two laws.

- 1. Regel: Wenn man map mit der Identify Funktion aufruft, bekommt man das gleiche zurück
- Regel: Wenn man zwei `maps` verknüpft, sollte das gleiche herauskommen, wie wenn man die beiden einzelnen Operationen in einem einzelnen `map` ausführt.

```swift
let names1 = names.map(uppercased).map(reversed)
let names2 = names.map(uppercasedAndReversed)
print(names1 == names2)
```


## Zusammenfassung
- Anwendung (Code)
- Auf welchen zwei wichtigen Nicht-Collections ist `map` ebenfalls unterstützt?


#nur learning unit#