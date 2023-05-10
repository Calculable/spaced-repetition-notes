# Methoden bei Structs und Enums
♻️

## Mutating Instanz-Methoden
- Können standartmässig die Properties des Typs nicht verändern (da es Value-Typen sind)

> However, if you need to modify the properties of your structure or enumeration within a particular method, you can opt in to mutating behavior for that method. 

```swift
struct Point {
    var x = 0.0, y = 0.0
    mutating func moveBy(x deltaX: Double, y deltaY: Double) {
        x += deltaX
        y += deltaY
    }
}
```

## Sich selbst einer neuen Instanz zuweisen
Es ist auch möglich, dass man sich selbst ein neues `self` zuweist:

```swift
mutating func moveBy(x deltaX: Double, y deltaY: Double) {
	self = Point(x: x + deltaX, y: y + deltaY)
}
```

Bei einem Enum wäre dass dann so aussehen:

```swift
self = .off
```
(Interessant z.B. für eine State-Machine)

## Konstante Structs / Enums
> Note that you can’t call a mutating method on a constant of structure type, because its properties can’t be changed, even if they’re variable properties

##  Zusammenfassung
- Wie funktionieren mutating Methoden auf einem Struct / Enum (syntax)


#learning unit#