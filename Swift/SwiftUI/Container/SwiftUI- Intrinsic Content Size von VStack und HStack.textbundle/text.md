# SwiftUI: Intrinsic Content Size von VStack und HStack

VStack und HStack nehmen nur den minimalen Platz ein, den Sie für ihren Inhalt benötigen:

```swift
var body: some View {
    VStack(alignment: .leading) {
        Text("Hello World")
        Text("Hello World 2")
    }
    .background(Color.red)
    .frame(maxWidth: .infinity, maxHeight: .infinity,
alignment: .topLeading)
    .padding()
}
```

![][image-1]

Das funktioinert natürlich nur, wenn alle Elemente eine vordefinierte Grösse haben. 

Hier wurde zum Beipsiel noch eine Farbe hinzugefügt, jetzt sieht es so aus:

![][image-2]

## Siehe auch UIKit
[ulysses://x-callback-url/open?id=P0yTEg9SyGmCJ0PCPOsHdw][1]

##  Zusammenfassung
- Wie gross ist ein HStack oder ein VStack

[1]:	ulysses://x-callback-url/open?id=P0yTEg9SyGmCJ0PCPOsHdw

[image-1]:	assets/Bildschirmfoto%202024-04-08%20um%2021.19.26.png
[image-2]:	assets/Bildschirmfoto%202024-04-08%20um%2021.20.07.png

#learning unit#