# Selection Navigation  🧭

(evt. deaktivieren)

## Codebeispiel

```swift
var body: some View {
    NavigationSplitView {
        List(colors, id: \.self, selection: $selection) { color in
            NavigationLink(color.description, value: color)
        }
    } detail: {
        if let color = selection {
            ColorDetail(color: color)
        } else {
            Text("Pick a color")
        }
    }
}
```

## Zusammenfassung
- Codebeispiel

#nur learning unit#