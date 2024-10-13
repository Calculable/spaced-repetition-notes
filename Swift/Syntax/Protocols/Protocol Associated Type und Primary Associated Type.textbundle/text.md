# Protocol Associated Type und Primary Associated Type
📜

## Für was sind Protocol Associated Types?

- Hinweis: Sollten wenn möglich vermieden werden
- Oft braucht man associated types, weil Protokolle keine generischen Parameter erlauben:

```swift
protocol Product {
	associatedtype Code
	var productCode: Code {get}
}

struct Laptop: Product {
	typealias Code = Int //braucht es oft nicht wegen Type Inference
	var productCode = 6 
}
```

## Primary Associated Type

Dieser Code hat ein Problem: Wir wollen zum Beispiel, dass innerhalb der Collection nur "Tracks" sein dürfen:

```swift
class MusicPlayer { 
	func play(_  playlist: some  Collection) { /* ... */ }
}
```

Deshalb kann man jetzt Primary Associated Types angeben (das sieht aus wie ein Generic). Hier ein Beispiel aus dem bereits existierenden Collection-Protokoll:

```swift
public protocol Collection<Element>: Sequence {
	associatedtype Element 
	associatedtype Iterator  =  IndexingIterator<Self>
	associatedtype SubSequence : Collection  =  ///...
}
```

Jetzt kann man es so verwenden:

```swift
class  MusicPlayer { 
	func  play(_  playlist: some  Collection<Track>) { /* ... */ }
}
```

Alternativ könnte man auch folgendes schreiben:

```swift
class  MusicPlayer {
	func  play<Playlist: Collection<Track>>(_  playlist: Playlist) { /* ... */ }
}
```

Ohne Primary Associated Types würde man folgendes schreiben:

```swift
class MusicPlayer {
    func play<T: Collection>(_ playlist: T) where T.Element == Track {
        /* ... */
    }
}
```


## Weitere Codebeispiele

```swift
let arraySequence: any Sequence<Int> = [1, 2, 3]
let rangeSequence: any Sequence<Int> = 4...6
let setSequence: any Sequence<Int> = Set([7, 8, 9])

// Now we can store all these different sequences in a single array
let sequenceArray: [any Sequence<Int>] = [arraySequence, rangeSequence, setSequence]

// Iterating through the array of existential sequences
for sequence in sequenceArray {
    for element in sequence {
        print(element)
    }
}
```


```swift
func makeSequence(condition: Bool) -> any Sequence<Int> {
    if condition {
        // Return an array-based sequence
        return [1, 2, 3, 4, 5]
    } else {
        // Return a range-based sequence
        return 1...5
    }
}

// Usage
let sequence: any Sequence<Int> = makeSequence(condition: true)
for element in sequence {
    print(element)
}
```

## Associated Type auf Protokoll einschränken

```swift
protocol Identifiable2 {
    associatedtype ID: Hashable
    var id: ID { get set }
}
```


#learning unit# #guide