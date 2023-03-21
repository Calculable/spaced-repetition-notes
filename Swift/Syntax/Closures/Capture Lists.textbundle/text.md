# Capture Lists
🦋

## Beispielcode

```swift
func sing() -> () -> Void {
    let taylor = Singer()

    let singing = {
        taylor.playSong()
        return
    }

    return singing
}
```

## Strong Capture (Default)

> The closure will capture any external values that are used inside the closure, and make sure they never get destroyed.

(in diesem Fall also das Objekt "taylor" innerhalb der Singing-Closure


## Weak Capture

```swift
func sing() -> () -> Void {
    let taylor = Singer()

    let singing = { [weak taylor] in
        taylor?.playSong()
        return
    }

    return singing
}
```

Die Objekte können zerstört werden und auf nil gesetzt werden. Deshalb arbeitet man mit Optionals

(In diesem Fall würde es nichts ausgeben, weil `taylor` schon entfernt wäre zum Zeitpunkt wo wir es aufrufen)

Generell: Dasjenige Objekt, dass weniger „ownership“ über das andere hat, sollte eine schwache Referenz halten.



## Unowned Capture

Ist eigentlich eine `weak` Reference, aber es verhält sich wie ein force-unwrapped optional.

```swift
func sing() -> () -> Void {
    let taylor = Singer()

    let singing = { [unowned taylor] in
        taylor.playSong()
        return
    }

    return singing
}
```

(In diesem Fall würde es Crashen, weil `taylor` schon entfernt wäre zum Zeitpunkt wo wir es aufrufen)

Man sollte es nur verwenden, wenn man sicher ist, dass es nicht nil wird.


## Zusammenfassung
- Was ist Capturing?
- Auf welche drei Arten kann man Values "capturen"

#learning unit#