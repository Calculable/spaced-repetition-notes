# Generics
🎉

##  Generische Funktion
```swift
func makeArray<Item>(repeating item: Item, numberOfTimes: Int) -> [Item] {
    var result = [Item]()
	//...    
}
makeArray(repeating: "knock", numberOfTimes: 4)
```

## Generische Klassen, Enumerations und Strukturen
```swift
enum OptionalValue<Wrapped> {
    case none
    case some(Wrapped)
}
var possibleInteger: OptionalValue<Int> = .some(100)
```

## Naming Best Practice

> In most cases, type parameters have descriptive names, such as Key and Value. However, when there isn’t a meaningful relationship between them, it’s traditional to name them using single letters such as T, U, and V

## Generic Contraints
Siehe separates Kapitel

## Zusammenfassung
Generische Funktionen, Klassen, Structs, Enums