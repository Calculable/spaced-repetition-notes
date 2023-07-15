# UIButton: Target Action hinzufügen
👆

## Neu mit iOS 14
```swift
button.addAction(UIAction { [weak self] _ in
	//do something
}, for: .touchUpInside)
```

## Alt
```swift
myButton.addTarget(self, action: #selector(viewTapped(_:)), for: .touchUpInside)
```

```swift
@IBAction func viewTapped(_ sender: UIButton) {
	print("View tapped!")
}
```

Alternativ:

```swift
@objc
private func viewTapped...
```

##  Zusammenfassung
- UIKit: Button Action definieren (neue Syntax mit iOS 14)

#learning unit#