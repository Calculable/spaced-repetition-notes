# Die Initializer einer UIView
🛫

## Required: NSCoder Initializer

```swift
//Wird verwendet wenn Storyboards oder Nib Files eingesetzt werden. Ansonsten wird einfach ein Fehler geworfen
required init?(coder aDecoder: NSCoder) {
    //super.init(coder: aDecoder)
	//....
	fatalError("not supported")
}
```

## Frame initializer

```swift
convenience init() {
	//.zero kann man verwenden, wenn man die View sowieso anschliessend mit Constraints plaziert
    self.init(frame: .zero)
}

override init(frame: CGRect) {
    super.init(frame: frame)
}
```

- Relativ zur Superview

##  Zusammenfassung
- Welcher Initializer muss zwingend angeboten werden?
- Wie kann man einen Initializer ohne Parameter anbieten?

#learning unit#