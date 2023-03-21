# Context Menu


## Bild

![][image-1]

## Code

```swift
Text("Change Color")
	.padding()
	.contextMenu {

		Button("Red") {
			backgroundColor = .red
		}
		
		Button("Green") {
			backgroundColor = .green
		}
		
		Button("Blue") {
			backgroundColor = .blue
		}
	}
```


## Die Buttons können auch eine Rolle haben

```swift
Button(role: .destructive) {
    backgroundColor = .red
} label: {
    Label("Red", systemImage: "checkmark.circle.fill")
}
```


##  Zusammenfassung
- Was ist ein Context Menu, wie sieht es aus?
- Wie macht man ein Context Menu?

[image-1]:	assets/Bildschirmfoto%202022-08-11%20um%2017.31.58.png

#learning unit#