# Invarianz, Covarianz, Contravarianz, Bivarianz 🦆

##  Invarianz

Folgendes ist nicht möglich, die Typen müssen exakt gleich sein:

```swift
Stack<Graphic> stack = new Stack<Rectangle>();
```

## Covarianz

```swift
Stack<? extends Graphic> stack;
```

Hier ist nur lesender Zugriff erlaubt und nicht Schreiben (weil man ja nicht weiss, welchen Typ genau erwartet wird beim Schreiben)

## Contravarianz

```swift
Stack<? super Graphic> stack
```

Hier ist nur Schreiben erlaubt aber nicht lesen, weil man ja nicht weiss, welchen Typ man zurückbekommen würde (man bekommt `Object` oder tiefer…)

## Bivarianz

```swift
Stack<?>
```

## Zusammenfassung
Was bedeuten die drei Begriffe?

#nur learning unit#