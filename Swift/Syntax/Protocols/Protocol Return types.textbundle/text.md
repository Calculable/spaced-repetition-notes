# Protocol Return types
📜

## Beispiel
```swift
//Return Protocol Type
func protoFlip<T: Shape>(_ shape: T) -> Shape {
    return FlippedShape(shape: shape)
}
```

- Man darf an verschiedenen Stellen im Body unterschiedliche Typen von Shape zurückgeben
- ` protoFlip(protoFlip(smallTriange)) ` ist hier nicht möglich (weil der Compiler nicht weiss, was er beim Verschachtelten Aufruf für den generischen Typ T verwenden soll)

=\> Lösung: Opaque Return Types

## Zusammenfassung
- Was ist ein Problem, wenn man ein Protokoll als Rückgabetyp verwendet?

#learning unit#