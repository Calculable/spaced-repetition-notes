# ForEach
♻️

## Range
```
ForEach(0..<100) { number in
        Text("Row \(number)")
}
```
 
::Hinweis: ForEach funktioniert noch nicht mit ClosedRanges (z.B. 1…5), vielleicht ändert sich das noch in der Zukunft…:

## Sequenz
```swift
ForEach(strings, id:\.self) {
        Text("Row \($0)")
}
```

## Zusammenfassung
- ForEach mit Range und Sequenz