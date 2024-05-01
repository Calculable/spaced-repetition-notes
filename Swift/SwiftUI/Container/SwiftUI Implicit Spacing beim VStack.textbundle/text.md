# SwiftUI Implicit Spacing beim VStack

Ein VStack in SwiftUI had ein implizites Padding. Das kann zu unerwartetem Verhalten führen:

![][image-1]

Begründung: Im ersten Beispiel mit Padding 0 hat man noch kein implizites Spacing. Beim mittleren Beispiel kommt zusätzlich zum Padding noch das implizite Spacing des Stacks dazu (welches sich eingeschatlet hat)

So kann man das Verhalten aber explizit festlegen:

```swift
VStack(alignment: .leading, spacing: 0) {/*...*/}
```

[image-1]:	assets/Bildschirmfoto%202023-07-30%20um%2012.57.43.png

#learning unit#