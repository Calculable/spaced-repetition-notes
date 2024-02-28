# Selection Navigation
🧭


## Vorlage


```swift
struct ContentView: View {
    let colors: [Color] = [.red, .green, .blue, .orange, .purple, .yellow]

    @State private var selection: Color?

    var body: some View {
        NavigationSplitView {
			//....
        } detail: {
            //....
        }
    }
}
```


![][image-1]

## Lösung

```swift
struct ContentView: View {
    let colors: [Color] = [.red, .green, .blue, .orange, .purple, .yellow]

    @State private var selection: Color?

    var body: some View {
        NavigationSplitView {
            List(colors, id: \.self, selection: $selection) { color in
                NavigationLink(color.description, value: color)
            }
        } detail: {
            if let color = selection {
                color
            } else {
                Text("Pick a color")
            }
        }
    }
}
```


## Zusammenfassung
- Codebeispiel mit einer Navigation Split View

[image-1]:	assets/Bildschirmfoto%202023-12-27%20um%2008.42.33.png

#learning unit#