# Any vs. Some
🌫️

## Um was geht es?
 - Wenn man ein Protokoll als Paramtertyp verwendet
- Früher war das Keyword `any` optional, mit Swift 6 wird es verpflichtet

## Any

```swift
func collides(with: any Shape) -> Bool
```

- Mit `any` wird deutlich gemacht, dass es Performance-Einbussen gibt
- Dafür kann man zur Laufzeit eine beliebige Implementation haben


##  Some

### Beispiel
Bei `some` Hingegen muss man bereits zur Compile-Zeit wissen, welchen Typ man bekommt:

```swift
func collides(with: some Shape) -> Bool
```

- Zur Compilezeit wird dann für jeden verwendeten aufruf-typ eine eigene Variante erzeugt
- Man sagt dem auch **opaque parameter declaration**

### Alternative
Früher hätte man das so schreiben müssen:

```swift
func collides<T: Shape>(with shape: T) -> Bool
```

### Some muss immer den gleichen Typ haben:


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


### Some als Rückgabewert

```swift
//Opaque Return Type
func flip<T: Shape>(_ shape: T) -> some Shape {
    return FlippedShape(shape: shape)
}
```

- Man darf NICHT  an verschiedenen Stellen im Body unterschiedliche Typen von Shape zurückgeben
- In Wahrheit gibt man immer noch einen konkreten Typen zurück
- Aber hier geht es darum, dass man die Implementation verstecken will.
- Wenn man einfach nur das Protokoll zurückgeben würde, dann wäre zum Beispiel `protoFlip(protoFlip(smallTriange))` nicht möglich, weil der Compiler nicht den Typ des ersten Results bestimmen kann (T), ohne dass er den Code ausführen würde.


#learning unit# #guide