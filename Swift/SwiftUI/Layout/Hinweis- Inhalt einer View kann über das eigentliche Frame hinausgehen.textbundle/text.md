# Hinweis: Inhalt einer View kann über das eigentliche Frame hinausgehen
🖼️

## Beispiel

```swift
struct ContentView: View {

    @State var showDropdown = false

    var body: some View {

        VStack {
            VStack {
                Button("Toggle") {
                        showDropdown.toggle()

                }

                if showDropdown {
                    OptionsView()
                }
            }
            .frame(width: 100, height: 50, alignment: .top)
            .border(.black)

            Text("Hello World")
        }
    }
}

struct OptionsView: View {
    var body: some View {
        Color.red
            .frame(height: 150)
    }
}
```

![][image-1]

##  Verhindern dass der Inhalt über das Frame geht

```swift
.frame(width: 100, height: 50, alignment: .top)
.clipped()
```

![][image-2]

[image-1]:	assets/2024-04-10%2008.08.16.gif
[image-2]:	assets/2024-04-10%2008.09.57.gif

#learning unit#