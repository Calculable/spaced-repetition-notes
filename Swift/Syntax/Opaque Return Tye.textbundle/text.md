# Opaque Return Tye
::27::

##  Beispiel
```swift
//Opaque Return Type
func flip<T: Shape>(_ shape: T) -> some Shape {
    return FlippedShape(shape: shape)
}
```

- Man darf NICHT  an verschiedenen Stellen im Body unterschiedliche Typen von Shape zurückgeben
- In Wahrheit gibt man immer noch einen konkreten Typen zurück
- Aber hier geht es darum, dass man die Implementation verstecken will.

## Wozu ist das gut?

Wenn man einfach nur das Protokoll zurückgeben würde, dann wäre zum Beispiel `protoFlip(protoFlip(smallTriange))` nicht möglich, weil der Compiler nicht den Typ des ersten Results bestimmen kann (T), ohne dass er den Code ausführen würde.