# Timeline View
⏱️

```swift
struct ContentView: View {
    let startDate = Date()

    let rainColor = Color(red: 0.25, green: 0.5, blue: 0.75)

    var body: some View {
        TimelineView(.animation) { timeline in
                Rectangle()
                    .frame(width: 100, height: 100, alignment: .center)
                    .foregroundStyle(.red.gradient)
                    .rotationEffect(.degrees(timeline.date.distance(to: startDate))*100)
        }
    }
}
```

![][image-1]

`.animation` zeichnet so schnell wie möglich

Statt `.animation` kann man auch angeben, wie oft die Animation wiederholt werden soll. Beachte: Weil man mit `Date` arbeitet spielt es keine Rolle, wie schnell die Bildwiederholungsrate des Gerätes ist

Details: [https://www.hackingwithswift.com/quick-start/swiftui/how-to-create-custom-animated-drawings-with-timelineview-and-canvas][1]

##  Zusammenfassung
- Konzept: Wie macht man eine Animation mit der Timeline View?

[1]:	https://www.hackingwithswift.com/quick-start/swiftui/how-to-create-custom-animated-drawings-with-timelineview-and-canvas

[image-1]:	assets/2024-02-11%2010.53.49.gif

#learning unit#