# Die Initializer eines UIViewController
🛫

## Required: NSCoder Initializer

```swift
//Wird verwendet wenn Storyboards oder Nib Files eingesetzt werden. Manchmal wird hier auch einfach ein `fatalError()` geworfen.
required init?(coder aDecoder: NSCoder) {
    super.init(coder: aDecoder)
	//....
}
```

## Nib Initializer

```swift
convenience init() {
    self.init(nibName: nil, bundle: nil)
}
```

Beachte: Es gibt keinen Frame initializer, das ist bei der UIView der Fall! ([ulysses://x-callback-url/open?id=X4JD4oVg-Jl8eatoXKCOqg][1])

## Was macht man im Init?

=\> Hier ist die View noch nicht verfügbar!

- Properties initialisieren
- Data source initialisieren
- Notification abonnieren

##  Zusammenfassung
- Welcher Initializer muss zwingend angeboten werden?
- Wie kann man einen Initializer ohne Parameter anbieten?

[1]:	ulysses://x-callback-url/open?id=X4JD4oVg-Jl8eatoXKCOqg

#learning unit#