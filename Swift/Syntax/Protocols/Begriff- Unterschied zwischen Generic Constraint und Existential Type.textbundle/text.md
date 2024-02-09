# Begriff: Unterschied zwischen Generic Constraint und Existential Type
📄

Idealerweise werden Protokolle in Kombination mit Generic Constraints verwendet:

```swift
func travel<T: TravelMethod>(using method: T) {
    print("I'm traveling at \(method.maxSpeed) miles per hour!")
}
```

Hier spricht man NICHT von existential type. Hier hingegen schon:


```swift
var method: TravelMethod = Car()
```

## Zusammenfassung
- Wann spricht man von Existential Type und wann nicht?


#nur learning unit# #learning unit#