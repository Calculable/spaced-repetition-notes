# Observable Makro für SwiftUI - Container
📦

## Container wie Optionals, Arrays etc. werden automatisch unterstützt und State-Changes erkannt

```swift
@Observable class Donut {
  var name: String
}

struct DonutList: View {
  var donuts: [Donut]
  var body: some View {
    List(donuts) { donut in
      HStack {
        Text(donut.name)
        Spacer()
        Button("Randomize") {
          donut.name = randomName()
        }
      }
    }
  }
}
```

> You can have arrays of observable models or even observable types that contain other observable types.

#learning unit#