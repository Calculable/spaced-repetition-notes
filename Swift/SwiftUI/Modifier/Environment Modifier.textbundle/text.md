# Environment Modifier

- Einige Modifier können auf Container angewannt werden. Das heisst - sie werden auf mehrere Views gleichzeitig angewant:

```swift
VStack {
    Text("Gryffindor")
        .font(.largeTitle) //überschreibt environment modifier
    Text("Hufflepuff")
    Text("Ravenclaw")
    Text("Slytherin")
}
.font(.title)
```

> To the best of my knowledge there is no way of knowing ahead of time which modifiers are environment modifiers and which are regular modifiers other than reading the individual documentation for each modifier and hope it’s mentioned. 

## Zusammenfassung
- Was bedeutet der Begriff?

#learning unit#