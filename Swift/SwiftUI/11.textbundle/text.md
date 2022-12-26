# Navigation View
::11::

## Beispiel

```swift
NavigationView {
    Form {
        Section {
            Text("Hello, world!")
        }
    }
    .navigationTitle("SwiftUI")
}
```


## Title Display Mode verändern
Für kleinere Titel: 

```swift
.navigationBarTitleDisplayMode(.inline)

```

##  NavigationLink

```swift
NavigationLink {
	Text("New secondary")
} label: {
	Text("Hello, World!")
}
```
