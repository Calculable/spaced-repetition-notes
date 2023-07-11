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

## Frame initializer

```swift
convenience init() {
    self.init(nibName: nil, bundle: nil)
}

override init(nibName nibNameOrNil: String?, bundle nibBundleOrNil: Bundle?) {
    super.init(nibName: nibNameOrNil, bundle: nibBundleOrNil)
}
```

##  Zusammenfassung
- Welcher Initializer muss zwingend angeboten werden?
- Wie kann man einen Initializer ohne Parameter anbieten?

#learning unit#