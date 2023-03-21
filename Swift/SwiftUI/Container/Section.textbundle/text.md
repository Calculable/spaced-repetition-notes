# Section

- Eine Section hingegen trennt die Elemente visuell in einer Liste oder Form


![][image-1]



```swift
struct ContentView: View {
    var body: some View { 
        Form {
            Group {
                Section("Optional Titel") {
                   //...
                }
                
                Section("Optional Titel") {
                    //...
                }

            }

            Group {
                //...
            }
            
        }
    }
}
```

##  Section mit eigenem Header / Footer


```swift
Section {
	//...   
} header: {
    Text("How much tip do you want to leave?")
}
```

## Zusammenfassung
- Wie macht man eine Section
- Wie macht man eine Section mit Custom Header?

[image-1]:	assets/Bildschirmfoto%202022-07-20%20um%2017.46.06.png

#learning unit#