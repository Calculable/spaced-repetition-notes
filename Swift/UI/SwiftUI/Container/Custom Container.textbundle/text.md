# Custom Container

##  Beispiel
Siehe: [https://www.hackingwithswift.com/books/ios-swiftui/custom-containers][1]

```swift
struct GridStack<Content: View>: View {
  let rows: Int
  let columns: Int
  @ViewBuilder let content: (Int, Int) -> Content

  var body: some View {
    VStack {
      ForEach(0..<rows, id: \.self) { row in
        HStack {
          ForEach(0..<columns, id: \.self) { column in
            content(row, column)
          }
        }
      }
    }
  }
}
```

wenn man als Content mehrere View mitgeben möchte, macht man es so:

```swift
@ViewBuilder let answerContent: () -> Content
```


## Composition

Man will, dass der Container auch mit Views funktioniert wenn diese mit ForEach etc. erstellt wurden, wie zum Beispiel hier:

```swift
DisplayBoard {
    Text("Scrolling in the Deep")
    Text("Born to Build & Run")
    Text("Some Body Like View")

    ForEach(songsFromSam) { song in
        Text(song.title)
    }
}
```

```swift
@ViewBuilder var content: Content

var body: some View {
    DisplayBoardCardLayout {
        ForEach(subviewOf: content) { subview in
            CardView {
                subview
            }
        }
    }
    .background { BoardBackgroundView() }
}
```

Mit dem `subviewOf` werden die xx statt die declared subviews verwendet:

![][image-1]
![][image-2]
![][image-3]

Wenn man zählen möchte, wie viele Views es sind:

```swift
@ViewBuilder var content: Content

var body: some View {
    DisplayBoardCardLayout {
        Group(subviewsOf: content) { subviews in
			//subviews.count
            ForEach(subviews) { subview in
                CardView {
                    subview
                }
            }
        }
    }
    .background { BoardBackgroundView() }
}

```

##  Sections

Optional kann man Sections unterstützen:

```swift
DisplayBoard {
    Section("Matt's Favorites") {
        Text("Scrolling in the Deep")
        Text("Born to Build & Run")
        Text("Some Body Like View")
    }

    Section("Sam's Favorites") {
        ForEach(songsFromSam) { song in
            Text(song.title)
        }
    }

    Section("Sommer's Favorites") {
        ForEach(songsFromSommer) { song in
            Text(song.title)
        }
    }
}
```

## Customization mit Container Values

Zum Beispiel kann die normale SwiftUI Liste auf den `listRowReparator`-Modifier zugreifen:


```swift
// SwiftUI Lists

List {
    Section("Favorite Songs") {
        Text("Scrolling in the Deep")
        Text("Born to Build & Run")
        Text("Some Body Like View")
    }

    Section("Other Songs") {
        ForEach(otherSongs) { song in
            Text(song.title)
                .listRowSeparator(.hidden)
        }
    }
}

```


Unterschied zu Environment Values und Preference Values:
- Auf Container Values kann nur der direkte Parent-Container zugreifen:

![][image-4]![][image-5]![][image-6]

So wird es definiert:

```swift
// Custom container values

extension ContainerValues {
    @Entry var isDisplayBoardCardRejected: Bool = false
}

extension View {
    func displayBoardCardRejected(_ isRejected: Bool) -> some View {
        containerValue(\.isDisplayBoardCardRejected, isRejected)
    }
}

```

```swift
struct DisplayBoardSectionContent<Content: View>: View {
    @ViewBuilder var content: Content

    var body: some View {
        DisplayBoardCardLayout {
            Group(subviewsOf: content) { subviews in
                ForEach(subviews) { subview in
                    let values = subview.containerValues
                    CardView(
                        scale: (subviews.count > 15) ? .small : .normal,
                        isRejected: values.isDisplayBoardCardRejected
                    ) {
                        subview
                    }
                }
            }
        }
    }
}
```
## Siehe auch Custom Layout

- Meistens verwendet man einen Custom Container und darin dann ein Custom Layout:

[ulysses://x-callback-url/open?id=jMz8vB4NKjJHtdgruXPPug][2]

##  Siehe

[WWDC 2024: Demystify SwiftUI containers][3]

[1]:	https://www.hackingwithswift.com/books/ios-swiftui/custom-containers
[2]:	ulysses://x-callback-url/open?id=jMz8vB4NKjJHtdgruXPPug
[3]:	https://developer.apple.com/wwdc24/10146

[image-1]:	assets/DraggedImage.png
[image-2]:	assets/DraggedImage-1.png
[image-3]:	assets/DraggedImage-2.png
[image-4]:	assets/IMG_2039.PNG
[image-5]:	assets/IMG_2040.PNG
[image-6]:	assets/IMG_2041.PNG

#guide