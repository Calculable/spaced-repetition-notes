# Für was braucht man Type Erasure?
❎

 - Das Problem ist dass es keine Generics für Protokolle gibt
- Stattdessen verwendet man Protocol Associated Types
- Ist dies der Fall, dann kann das Protokoll nicht mehr als Existential Typ verwendet werden =\> Der Compiler würde ja nicht wissen, mit welchem Typ das Protokoll arbeitet
- Achtung - Type Erasure Types sind keine Protokolle sondern Wrapper

##  Beispiel: Protocols mit Associated Types als Existential Type

Dieser Code wäre nicht möglich:

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

let electricCars: [Car] = [FamilyCar(), WorkCar()] //Use of protocol 'Car' as a type must be written 'any Car'
```

- Beachte: Seit Swift 5.7 ist dieses Problem nicht mehr so schlimm, teilweise ist die Verwendung als existential Type möglich:

```swift
let electronicCars: [any Car] = [FamilyCar(), WorkCar()]
```

Nun möchte man aber sicherstellen, dass im Array nur Elektronische Fahrzeuge drin sind. Deshalb schreibt man einen Type Erasure Typen:

```swift
struct AnyCar<Fuel>: Car {
   //Implementation
}

let electricCars: [AnyCar<Electricity>]  = [AnyCar(FamilyCar()), AnyCar(WorkCar())]
```


## Hinweis: Man könnte dieses Problem mittlerweile auch mit Primary Associated Types lösen

(seit Swift 5.7)
```swift
protocol Car<Fuel> {
    associatedtype Fuel
    func drive(fuel: Fuel)
}

let electricCars: [any Car<Electricity>] = [FamilyCar(), WorkCar()]
```


Siehe auch: **Type Erasure vs. Primary Associated Types**: [ulysses://x-callback-url/open?id=1oAvsqOUmaUbWCHZtmQPLQ][1]


## Zusammenfassung
- Beispiel für Type Erasure anhand vom Protocol `Car` und associated type `Fuel`

[1]:	ulysses://x-callback-url/open?id=1oAvsqOUmaUbWCHZtmQPLQ

#learning unit#