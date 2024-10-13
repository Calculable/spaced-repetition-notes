# Type Erasure?
❎

## Um was geht es?
- Type Erasure Typen sind zum Beispiel AnyView oder AnySequence
- Type Erasure Typen sind Wrapper um Protokolle, weil es keine Generics für Protokolle gibt, sondern nur Associated Types
- Durch Primary Associated Types wurden jedoch fast alle Anwendungsfälle von Type Erasure überflüssig. Man verwendet es aber noch häufig in Legacy Code

## Type Erasure Beispiel: AnySequence
❎

```swift
let seq = AnySequence<Int>([1,2,3])
```

- AnySequence ist kein Protokoll
- Sequence ist aber ein Protokoll das vom Array implementiert wird
- Sondern ein generisches Struct das eine andere Sequence wrappt
- Vorteil: Man hat eine Funktion und möchte eine Sequenz von Integer als Parameter entgegennehmen
- Neu könnte man jedoch oft auch einfach `Sequence<Int>` verwenden

## Welches Problem wird gelöst?

Man möchte zum Beispiel eine Sequenz mit Elektrischen Fahrzeugen machen:

```swift
protocol {
    associatedtype Fuel
    func drive(fuel: Fuel)
}

struct Electricity {}
struct Petrol {}

struct SportsCar: Car {
    func drive(fuel: Petrol) { print("🏎️") }
}

struct FamilyCar: Car {
    func drive(fuel: Electricity) { print("🚗") }
}

struct WorkCar: Car {
    func drive(fuel: Electricity) { print("🚙") }
}

let onlyElectricCars: ? = ?
```

## Lösung mit Type Erasure

```swift
struct AnyCar<Fuel>: Car {
   //Implementation
}

let electricCars: [AnyCar<Electricity>]  = [AnyCar(FamilyCar()), AnyCar(WorkCar())]
```

## Neue Lösung mit Primary Associated Types

Seit Swift 5.7 und Primary Associated Types kann man auch folgendes schreiben:

```swift
protocol Car<Fuel> {
    associatedtype Fuel
    func drive(fuel: Fuel)
}

let electricCars: [any Car<Electricity>] = [FamilyCar(), WorkCar()]
```

=\> Siehe auch ["Wann braucht man weiterhin Type Erasure?"][1]

## (Beispiel: Eigener Type Erasure Typ)

Aus dem Protokoll wird eine Klasse gemacht:

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

Jetzt kann man schreiben:

```swift
struct CacheItem {
    let item: AnyCachable<Any>
    let expiryDate: Date
    ...
}
let cache: [AnyCachable<String>] = [AnyCachable("Hello"), AnyCachable("World")]
```

[1]:	ulysses://x-callback-url/open?id=1oAvsqOUmaUbWCHZtmQPLQ

#learning unit# #guide