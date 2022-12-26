# ForEach
::10::

## Beispiele
```
ForEach(0..<100) { number in
        Text("Row \(number)")
}
```
 
::Hinweis: ForEach funktioniert noch nicht mit ClosedRanges (z.B. 1…5), vielleicht ändert sich das noch in der Zukunft…:

```swift
ForEach(strings, id:\.self) {
        Text("Row \($0)")
}
```

## Protokollanforderungen für `id: \.self `

- Wenn die Elemente das `Identifiable` Protokoll implementieren, dann braucht man `id: \.self` nicht
- Bei einem Struct wird bei `\.self` der Hashwert über alle Properties gebildet, wenn es nicht Identifiable ist (dazu muss es Hashable sein)
