# Type Erasure vs. Primary Associated Types
🥇

## Frage

```swift
protocol Car<Fuel> {
    associatedtype Fuel
    func drive(fuel: Fuel)
}

struct SportsCar: Car {
    func drive(fuel: Petrol) { print("🏎️") }
}

struct FamilyCar: Car {
    func drive(fuel: Electricity) { print("🚗") }
}

struct WorkCar: Car {
    func drive(fuel: Electricity) { print("🚙") }
}
```


## Ein Array erstellen, dass nur elektrische Fahrzeuge enthält

### Mit Type Erasure

```swift
struct AnyCar<Fuel>: Car {
   //Implementation
}

let electricCars: = [AnyCar(FamilyCar()), AnyCar(WorkCar())]
```

### Mit Primary Associated Type

```swift
let electricCars: [any Car<Electricity>] = [FamilyCar(), WorkCar()]
```

## Wann braucht man weiterhin Type Erasure?

###  Fall 1: Protokolle mit Self Requirement
- Zum Beispiel, wenn man Equatable implementieren möchte oder andere Typen mit `Self` requirement (Bei Equatable bedeutet das Self-Requirement zum Beispiel, dass nur zwei Objekte des gleichen Typs verglichen werden können)

Das wäre also nicht möglich mit Primary Associated Types:

```swift
protocol Car<Fuel>: Equatable {
    //...
}

let electricCars: [any Car<Electricity>] = [WorkCar(), WorkCar()]
electricCars[0] == electricCars[1] //🛑 <- Fehler!
```

Mit Type Erasure wäre es hingegen möglich:

```swift
let electricCars: [AnyCar<Electricity>] = [AnyCar(FamilyCar()), AnyCar(WorkCar()), AnyCar(WorkCar())]
electricCars[0] == electricCars[1] // ✅ false
electricCars[1] == electricCars[2] // ✅ true
```

### Fall 2: 

Hier kann man keinen `any Car` übergeben, wenn ein generischer Typ erwartet wird, der zu `Car` konform ist, kann man kein `any Car` übergeben  

```swift
struct Garage<GarageCar: Car> {
    init(car: GarageCar) {}
}
```

```swift
let anyCar: any Car = FamilyCar()
let anyCarGarage = Garage(car: anyCar) // Type 'any Car' cannot conform to 'Car' //🛑 <- Fehler!
```

Beachte: ein `any Car` entspricht also nicht dem Typ `Car`!


Mit Type Erasure wäre es hingegen möglich:

```swift
let explicitAnyCar = AnyCar(FamilyCar())
let anyCarGarage = Garage(car: explicitAnyCar)
```

##  Quelle

[https://stackoverflow.com/questions/76449655/swift-is-there-still-a-use-case-for-type-erasure-since-the-introduction-of-prim][1]

## Zusammenfassung
- In welchen zwei Fällen braucht man Custom Type Erasure Typen trotz Primary Associated Types (nur das ungefähre Konzept, nicht im Detail)

[1]:	https://stackoverflow.com/questions/76449655/swift-is-there-still-a-use-case-for-type-erasure-since-the-introduction-of-prim

#learning unit#