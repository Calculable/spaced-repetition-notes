# ScrollView
↕️

```swift
ScrollView {
    VStack(spacing: 10) {
        ForEach(0..<100) {
            Text("Item \($0)")
                .font(.title)
        }
    }
    .frame(maxWidth: .infinity) //das schreibt man, damit die Scroll View den ganzen Platz einnimmt und nicht nur das Minimum dass die Element brauchen
}
```



Zudem kann man definieren, ob man die ScrollView horizontal oder Vertikal haben will:

```swift
ScrollView(.horizontal) {

}
```


##  Zusammenfassung
- Wie macht man eine ScrollView

#learning unit#