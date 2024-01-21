# Bindable aus einer Environment-Variable erstellen
🖇️

```swift
struct ContentView: View {
    @Environment(Model.self) var model

    var body: some View {
        @Bindable var model = model
        
        TextField("", text: $model.someField)
    }
}
```

Scheint nötig zu sein, weil Environment-Objekte nicht standartmässig Bindalbe sind: [https://mastodon.social/@twostraws/111008327602937262][1]

## Zusammenfassung
- Syntax

[1]:	https://mastodon.social/@twostraws/111008327602937262

#learning unit#