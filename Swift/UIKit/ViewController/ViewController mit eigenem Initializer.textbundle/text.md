# ViewController mit eigenem Initializer
🏁

##  Zweck
- So kann man zum Beispiel Dependency Injection implementieren


##  Codebeispiel
```swift
init?(coder: NSCoder, title: String) {
    self.title = title
    super.init(coder: coder)
}

required init?(coder: NSCoder) {
    fatalError("You must create this view controller with a product.")
}
```

oder man kann auch ganz auf den Coder verzichten:

```swift
init(with foo: Foo) {
	self.foo = foo
	super.init(nibName: nil, bundle: nil)
}
```

##  Zusammenfassung
- Beispiel: Initializer mit Parameter, zweiter Initializer soll nicht aufgerufen werden können

#learning unit#