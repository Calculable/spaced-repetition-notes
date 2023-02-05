# Animation: Binding Changes 🚁


```swift
Stepper("Scale amount", value: $animationAmount.animation(
    .easeInOut(duration: 1)))
```

So werden alle Views animiert, die mit `animationAmount` arbeiten! `animationAmount` ist eine ganz normal Int-Variable. 

Es fühlt sich so an, als ob man animationAmount nicht sofort den nächsten Wert zuweist, sondern denn werd „sliden“ lässt

## Zusammenfassung
- Binding Changes animieren