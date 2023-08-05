# Popover View
🍾

```swift
Button("Show Menu") {
    showingPopover = true
}
.popover(isPresented: $showingPopover) {
    Text("Your content here")
        .font(.headline)
        .padding()
}
```

![][image-1]![][image-2]

## Zusammenfassung
- Popover view anzeigen
- Wie sieht es auf iPad vs. iPhone aus?

[image-1]:	assets/2023-08-04%2014.14.31.gif
[image-2]:	assets/2023-08-04%2014.15.11.gif

#learning unit#