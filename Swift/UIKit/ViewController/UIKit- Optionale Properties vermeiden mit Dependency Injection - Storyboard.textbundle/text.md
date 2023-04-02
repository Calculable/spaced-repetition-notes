# UIKit: Optionale Properties vermeiden mit Dependency Injection - Storyboard
💉

## Problem

In den ViewControllern hat man oft **implicitly unwrapped** optional Properties, weil man zwingend einen leeren Initializer braucht:


```swift
var title: String!
```

Beim erstellen des ViewControllers muss man daran denken, diese Properties zu setzen:

```swift
var myViewController = storyboard?.instantiateViewController(identifier: "MyViewController") as MyViewController!

myViewController.title = "New Title" //!
```

## Lösung (seit iOS 13)

- Zunächst einmal macht man zwei Initializer für den ViewController.
- Der erforderliche ViewController ohne Parameter wirft einfach einen Fehler-

```swift
init?(coder: NSCoder, title: String) {
    self.title = title
    super.init(coder: coder)
}

required init?(coder: NSCoder) {
    fatalError("You must create this view controller with a product.")
}
```

=\> Siehe separate Learning Unit: ViewController mit eigenem Initializer

Jetzt kann man die Methode `instantiateViewController` mit einem eigenen "Creator" aufrufen:

```swift
var myViewController = storyboard?.instantiateViewController(identifier: "MyViewController",  creator: { coder in 
	MyViewController(coder: coder, title: "MyTitle")
})
```

=\> Beachte: Den Parameter „Identifier“ braucht es nicht mehr zwingend.

#learning unit#