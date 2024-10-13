# Alignment

## Alignment für Frame

So kann man das Alignment festlegen:

```java
.frame(width: 300, height: 300, alignment: .topLeading)
```
(Das ist links oben in Links-zu-Rechts Sprachen)


##  Alignment für Stack

```java
HStack(alignment: .bottom)
```
![][image-1]

```java
HStack(alignment: .lastTextBaseline) {
```

![][image-2]

##  Alignment guide anpassen

Man hat dieses Beispiel:

```java
VStack(alignment: .leading) {
	Text("Hello, world!")
	Text("This is a longer line of text")
}
```

In diesem Beispiel fragt der VStack beide Texte, wo ihr Leading-Edge ist.
Beide Texte berechnen ihre benötigte grösse und können dann Die Koordinate ihrer Leading Edge zurückgeben. (Bei Links-zu-Rechts-Sprachen) ist das einfach der linkste Teil der View.

Man kann aber auch selbst anpassen, was für uns der Leading-Edge ist mit Hilfe dieser Funktion:

Die Funktion übergibt uns die Dimension also Grösse der View und wir können dann zurückgeben, wo die Leading-Edge sein soll.

```java
    Text("Hello, world!") //das ist das Standartverhalten.
        .alignmentGuide(.leading) { d in d[.trailing] }
```

```java
 .alignmentGuide(.leading) { _ in Double(-30)}
```

Achtung: Das ist nicht das gleiche wie ein Offset. Bei einem Offset bleiben der ursprüngliche Platz für die View erhalten.


##  Custom Alignment Guide

Das ist zum Beispiel hilfreich, wenn man zwei Elemente alignen will, die in der View-Hierarchie an völlig unterschiedlichen Orten stehen.

```java
struct ContentView: View {
    var body: some View {
        HStack {
            VStack {
                Text("@twostraws")
                Image("paul-hudson")
                    .resizable()
                    .frame(width: 64, height: 64)
            }

            VStack {
                Text("Full name:")
                Text("PAUL HUDSON")
                    .font(.largeTitle)
            }
        }
    }
}
```

![][image-3]


**So macht man den Custom Alignment Guide:**

```java
extension VerticalAlignment {
    struct MidAccountAndName: AlignmentID {
        static func defaultValue(in d: ViewDimensions) -> CGFloat {
            d[.top] //beachte - das ist nur der Default wert. Man gibt ihn nur an, für denn fall, dass man unten das Custom Alighnment zwar verwendet aber nur für den Stack und nicht für die einzelnen elemente anpasst
        }
    }

    static let midAccountAndName = VerticalAlignment(MidAccountAndName.self)
}
```
(Beachte: Statt struct kann man auch einfach Enum schreiben. Eigentlich macht das mehr sinn, weil aus einem Enum knn man keinse Instanz erzeugen)

Beachte: Die letzte Zeile ist eigentlich nur ein Hilfs-Wrapper, damit man nicht überall „Vertical Alignment“ schreiben muss

**So wird der Custom Alignment Guide angewendet:**

```java
HStack(alignment: .midAccountAndName) {
    VStack {
        Text("@twostraws")
            .alignmentGuide(.midAccountAndName) { d in d[VerticalAlignment.center] } //hier sagen wir: "Das Vertikale Zentrum dieses Objekts dient uns als Position für den "midAccountAndName" alignment-guide
        Image("paul-hudson")
            .resizable()
            .frame(width: 64, height: 64)
    }

    VStack {
        Text("Full name:")
        Text("PAUL HUDSON")
            .alignmentGuide(.midAccountAndName) { d in d[VerticalAlignment.center] }
            .font(.largeTitle)
    }
}
```


**So sieht das Resultat aus:**

![][image-4]

[image-1]:	assets/Bildschirmfoto%202022-08-21%20um%2012.12.38.png
[image-2]:	assets/Bildschirmfoto%202022-08-21%20um%2012.13.52.png
[image-3]:	assets/Bildschirmfoto%202022-08-21%20um%2012.52.18.png
[image-4]:	assets/Bildschirmfoto%202022-08-21%20um%2013.06.05.png

#guide