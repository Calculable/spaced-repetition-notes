# Animation
::22::

##  Variante 1: Animation an die View Binden


```swift
Button ("Tap Me") {
	animationAmount += 1
}
.scaleEffect(animationAmount)
.animation(.default, value: animationAmount)
```

## Variante 2: An den Value binden (Animate Binding Changes)

```swift
Stepper("Scale amount", value: $animationAmount.animation(
    .easeInOut(duration: 1)))
```

So werden alle Views animiert, die mit `animationAmount` arbeiten! `animationAmount` ist eine ganz normal Int-Variable. 

Es fühlt sich so an, als ob man animationAmount nicht sofort den nächsten Wert zuweist, sondern denn werd „sliden“ lässt

## Variante 3: Explizite Animationen

```swift
withAnimation(.interpolatingSpring(stiffness: 5, damping: 1)) {
    animationAmount += 360
}
```
