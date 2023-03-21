# Confirmation Dialog

- Können sehr viele Buttons haben (im Gegensatz zu Alert)
- Man kann es Dismissen, wenn man ausserhalb des Dialogs klickt

```swift
.confirmationDialog("Change background", isPresented: $showingConfirmation) {
    Button("Red") { backgroundColor = .red }
    Button("Green") { backgroundColor = .green }
    Button("Blue") { backgroundColor = .blue }
    Button("Cancel", role: .cancel) { }
} message: {
    Text("Select a new color")
}
```

![][image-1]

##  Zusammenfassung
- Wie sieht ein Confirmation Dialog aus?

[image-1]:	assets/Bildschirmfoto%202022-08-01%20um%2016.07.41.png

#learning unit#