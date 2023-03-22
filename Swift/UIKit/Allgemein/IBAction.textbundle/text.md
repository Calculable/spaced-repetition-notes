# IBAction
⚽️

## Code
```swift
@IBAction func buttonPressed(_ sender: UIButton){
	let text = inputTextField.text
	messageLabel.text = text
}
```

## Sender

- Der Sender optional, man muss ihn nicht als Argument angeben.

Man kann auch den sender-Tag auslesen:

```swift
sender.tag 
```

## Zusammenfassung
- Code
- Mit Sender / Tag arbeiten


#learning unit#