# Segue: Daten übergeben ➡️

## ViewController 1
```swift
override func prepare(for segue: UIStoryboardSegue, sender: Any?) {
	if segue.identifier == "NavigationToScreen2"  {
		let viewController2 = segue.destination as?  ViewController2
		viewController2?.text =  "Hello World"
	} else if segue.identifier == "NavigationToScreen3" {
		let viewController3 = segue.destination as? ViewController3
		viewController2?.text =  "Hello World 2"
	}
}
```

- Beachte: Wenn es nur einen Segue gibt, dann muss man den Identifier nicht überprüfen.
- Häufig übergibt man sich auch selbst der zweiten View als Delegate, Siehe auch: Delegation Pattern

## ViewController 2

Damit das funktioniert muss der andere `ViewController` folgendes Property haben:

```swift
var text: String!
```

Beachte: Das Ausrufezeichen wird benötigt, weil man ja ansonsten einen Initializer benötigen würde.

und im `viewDidLoad` muss dieses entsprechend angezeigt werden:

```swift
textLabel.text = text
```

## Zusammenfassung
- Wie kann man beim Segue der anderen View Daten mitgeben?


#nur learning unit#