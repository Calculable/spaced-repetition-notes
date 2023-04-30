# UIButton: Target Action hinzufügen
👆


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


#learning unit#