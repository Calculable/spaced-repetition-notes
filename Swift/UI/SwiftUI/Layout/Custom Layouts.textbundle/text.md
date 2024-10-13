# Custom Layouts


## Beispiel: Radial Layout
 - Neu seit iOS 16: Layout Protokoll


> For example, we could implement a radial layout – a layout that places it views around a circle:

```swift
struct RadialLayout: Layout {

	//sizeProposal ist der verfügbare Platz des Parents
    func sizeThatFits(proposal: ProposedViewSize, subviews: Subviews, cache: inout Void) -> CGSize {
        // proposal.replacingUnspecifiedDimensions wird aufgerufen weil die vorgeschlagene Grösse manchmal nil-Werte enthält. Diese werden hier ersetzt. In diesem Beispiel akzeptiert die View einfach die vorgeschlagene Grösse des Parents. 
        proposal.replacingUnspecifiedDimensions()
    }

    func placeSubviews(in bounds: CGRect, proposal: ProposedViewSize, subviews: Subviews, cache: inout Void) {
        let radius = min(bounds.size.width, bounds.size.height) / 2
        let angle = Angle.degrees(360 / Double(subviews.count)).radians
        for (index, subview) in subviews.enumerated() {
            let viewSize = subview.sizeThatFits(.unspecified)
            let xPos = cos(angle * Double(index) - .pi / 2) * (radius - viewSize.width / 2)
            let yPos = sin(angle * Double(index) - .pi / 2) * (radius - viewSize.height / 2)
            let point = CGPoint(x: bounds.midX + xPos, y: bounds.midY + yPos)
            subview.place(at: point, anchor: .center, proposal: .unspecified)
        }
    }
}
```


## Zugriff auf Informationen in den Subviews

- Es ist nicht möglich auf die eigentlichen Subviews zuzugreifen, sondern nur auf Proxies davon (typ `Subviews`)
- Inerhalb der Subviews kann man jedoch mit dem `layoutValue` Modifier informationen hinterlegen.
- Beispiel:


Die Views sollen einen Rank haben. Man macht:

```swift
private struct Rank: LayoutValueKey {
  static let defaultValue: Int = 1
}

extension View {
  func rank(_ value: Int) -> some View { // 👈🏻 convenience method
    layoutValue(key: Rank.self, value: value) // 👈🏻 the new modifier
  }
}
```

Jetzt kann man es so verwenden:

```swift
MyCustomLayout {
	myView
		.rank(3)
	myView
		.rank(5)
}
```

Innerhalb des Layouts kann man dann so auf den Rank zugreifen:

```swift
subview[Rank.self]
```

## Anwenden des Custom Layouts

Genau gleich wie System-Container
```swift
RadialLayout {
	OtherView()
	OtherView()
	OtherView()
}
```

##  AnyLayout

Falls man so etwas machen möchte:

```swift
var body: some View {
  let layout = myCondition ? AnyViewLayout(HStack()) : AnyViewLayout(MyRadialLayout())

  layout {
    myView
  }
}
```

##  Beispiel Layout zum Debugging

Hier sieht man, welche grösse vorgeschlagen wird und wie die Views effektiv positioniert werden:

```swift
struct DebugLayout: Layout {
    let name: String

    func sizeThatFits(proposal: ProposedViewSize,
                      subviews: Subviews,
                      cache: inout ()) -> CGSize {
        let result = subviews[0].sizeThatFits(proposal)
        print(name, proposal, result)
        return result
    }
    
    func placeSubviews(in bounds: CGRect,
                       proposal: ProposedViewSize,
                       subviews: Subviews,
                       cache: inout ()) {
        subviews[0].place(at: bounds.origin, proposal: proposal)
    }
}

extension View {
    func debugLog(_ name: String) -> some View {
        DebugLayout(name: name) { self }
    }
}
```


## Siehe auch Custom Container
[ulysses://x-callback-url/open?id=ahlk98kqcE-dxN0\_ZuMRYg][1]

##  Quelle
[https://www.wwdcnotes.com/notes/wwdc22/10056/][2]
[https://www.swiftuifieldguide.com/layout/debugging/][3]

[1]:	ulysses://x-callback-url/open?id=ahlk98kqcE-dxN0_ZuMRYg
[2]:	https://www.wwdcnotes.com/notes/wwdc22/10056/
[3]:	https://www.swiftuifieldguide.com/layout/debugging/

#guide