# Try
::22::

## Try = Propagieren

Propagiert den Fehler, falls er auftritt
```swift
init(name: String, vendingMachine: VendingMachine) throws {
	try vendingMachine.vend(itemNamed: name)
     self.name = name
}
```

## Try? = Bei Error Nil zurückgeben

- So wird also ein Optional daraus gemacht

```swift
let printerFailure = try? send(job: 1885, toPrinter: "Never Has Toner")
```

##  Try! = Bei Error einen Runtime-Error werfen

Vor allem dann, wenn man weiss dass kein Fehler auftreten kann
```swift
let photo = try! loadImage(atPath: "./Resources/John Appleseed.jpg")
```

