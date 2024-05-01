# Class Constraint 
⛓️

##  Was ist ein Class Constraint?

Nur Klassen sollen das Protokoll implementieren dürfen, keine Structs?

```swift
protocol MyProtocol: AnyObject {}
```


## Warum macht man das häufig?
- Damit jemand der das Protokoll verwendet das Objekt mit `weak` Referenzieren kann.
- Beim [Delegate-Pattern][1] wird das zum Beispiel so gemacht:

```swift
protocol DiceGameDelegate: AnyObject {
	//...
}

class DiceGame {
	weak var delegate: DiceGameDelegate?
	func play() {
		delegate?.gameDidStart(self)
		//...
	}
}
```

- Doch es ist nicht nur auf Delegates begrenzt, sondern überall dort wo ein Zyklus entstehen könnte:

![][image-1]

## Weitere mögliche Gründe für einen Class Constraint

- Man möchte Identity Checking verwenden können (objectA === objectB)
- Man will dass das Protokoll mit Objective-C Kompatibel ist

##  Zusammenfassung
- Was ist ein Class Constraint?
- Warum braucht man es zum Beispiel beim Delegate Pattern?

[1]:	ulysses://x-callback-url/open?id=v8WGlrR69n6d4iar_RTrmA

[image-1]:	assets/DraggedImage.png

#learning unit#