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
![][image-1]

## Man kann auch eine IBAction an eine bereits bestehende Funktion hängen

![][image-2]


## Zusammenfassung
- Code
- Mit Sender / Tag arbeiten

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-04-01%20um%2015.38.48.png
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-03-17%20um%2007.45.59.png

#learning unit#