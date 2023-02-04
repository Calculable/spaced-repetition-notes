# Type Erasure ❎
::17::

## Für was braucht man Type Erasure?

 - Das Problem ist dass es keine Generics für Protokolle gibt
- Stattdessen verwendet man Protocol Associated Types
- Ist dies der Fall, dann kann das Protokoll nicht mehr als Existential Typ verwendet werden. (Weil man könnte das Protokoll ja gar nicht richtig verwenden, wenn man nicht weiss, welche Typen darin gespeichert sind.
- (Beachte: Seit Swift 5.7 ist dieses Problem nicht mehr so schlimm, teilweise ist die Verwendung als existential Type möglich. Zudem gibt es neu die Primary Associated Types)
	 

- Hier ist eine sehr gute Erklärung: [https://robnapier.net/erasure][1]
- Siehe auch: Protocol Associated Type.

- Wir können eine `AnyXY<T>`-Klasse bauen, um das Problem zu beheben. Diese ist ein wie ein Wrapper.



## Vordefinierte `Any`-Typen:

z.B. `AnyView`, `AnySequence`, …

```swift
let seq = AnySequence<Int>([1,2,3])
//This creates an AnySequence<Int>.
```

> Notice that `AnySequence` is not a protocol. It’s a generic struct that wraps another sequence. You can’t use an `[Int]` in a place that expects an `AnySequence<Int>`. You still want to use SequenceType for parameters in most cases.

##  Unterschied zu Any und AnyObject

These “Any” type erasers also aren’t like Any and AnyObject, which are protocols that just “hide” the type. You can still as! an AnyObject back to its original type. AnySequence and its kin completely encapsulate the underlying data. You can’t get the original back. This creates a very strong abstraction layer and strengthens type safety by making as! casting impossible.


##  Eigener `Any` -Typ (nicht auswändig können, nur verstehen)

### Definition
Wir können eine `AnyXY<T>`-Klasse bauen, um das Problem zu beheben:

```swift
class AnyCachable<T>: Cachable {    
    private let _decode: (_ data: Data) -> T?
    private let _encode: () -> Data?
    init<U: Cachable>(_ cachable: U) where U.CacheType == T {
        _decode = cachable.decode
        _encode = cachable.encode
    }
    func decode(_ data: Data) -> T? {
        return _decode(data)
    }
    func encode() -> Data? {
        return _encode()
    }
}
```


###  Verwenden des eigenen `Any` -Typs

Jetzt kann man schreiben:

```swift
struct CacheItem {
    let item: AnyCachable<Any>
    let expiryDate: Date
    ...
}
let cache: [AnyCachable<String>] = [AnyCachable("Hello"), AnyCachable("World")]
```


## Zusammenfassung
Zweck
Vordefinierte Any-Typen anwenden
Unterschied zu Any/AnyObject

[1]:	https://robnapier.net/erasure