# idealWidth und idealHeight für SwiftUI 
↕️
(intrinsic content size)

## Hinweise

- `idealWidth und idealHeight` sind nur Vorschläge. Die Grösse kann weiterhin durch den Container bestimmt werden


## Beispiel: Ausgangslage

```swift
struct MyCustomView: View {
    var body: some View {
        Color.red
            .frame(idealWidth: 200, idealHeight: 100)
    }
}
```

## Beispiel: Ohne Layout-Einschränkung

```swift
var body: some View {
    MyCustomView()
}
```

Ignoriert die ideal-size und nimmt den gesamten Platz ein:

![][image-1]

## Beispiel: Mit fixedSize()

```swift
var body: some View {
    MyCustomView()
        .fixedSize()
}
```

- ideal-size wird eingehalten:

![][image-2]

##  Beispiel: Mit aspectRatio ohne Parameter


```swift
var body: some View {
    MyCustomView()
        .aspectRatio(contentMode: .fit)
}
```

- die aspectRatio der idealSize wird verwendet:

![][image-3]

## Beispiel: In einem Scroll-View

```swift
var body: some View {
        ScrollView {
            VStack {
                MyCustomView()
                Text("Example")
                MyCustomView()
            }
        }
    }
}
```

Hier wird die Höhe berücksichtigt, die Breite jedoch nicht:

![][image-4]


## Quelle

[https://www.swiftuifieldguide.com/layout/ideal-size/][1]

##  Zusammenfassung
- Wie wird die idealWidth / idealHeight gesetzt?
- Wie verhält es sich ohne Layoutvorgaben
- Wie verhält es sich mit fixedSize Modifier?
- Wie verhält es sich in einer Scroll View

- Wie kann man es bei `.aspectRatio` nutzen?

[1]:	https://www.swiftuifieldguide.com/layout/ideal-size/

[image-1]:	assets/Bildschirmfoto%202024-03-31%20um%2009.18.47.png
[image-2]:	assets/Bildschirmfoto%202024-03-31%20um%2009.19.14.png
[image-3]:	assets/Bildschirmfoto%202024-03-31%20um%2009.20.47.png
[image-4]:	assets/Bildschirmfoto%202024-03-31%20um%2009.26.30.png

#learning unit#