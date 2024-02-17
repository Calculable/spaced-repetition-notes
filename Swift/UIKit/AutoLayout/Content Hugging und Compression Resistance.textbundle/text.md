# Content Hugging und Compression Resistance
↕️

## Theorie

- **Intrinsic Content Size**: "die natürliche Grösse". Details: [ulysses://x-callback-url/open?id=QI0hpMFrXUpqEpjZRzsK1Q][1]
- **Content Compression Resistance**: wir stark will das Objekt nicht kleiner werden
- **Content Hugging**: wie stark will das Objekt nicht wachsen („hält sich zusammen“)


## Gröse im Code setzen

### Beispiel: Label

```swift
cluesLabel.setContentHuggingPriority(UILayoutPriority(1), for: .vertical)
```

Es gibt auch definierte Konstanten, wie zum Beispiel `. required`

Dann kann man in Xcode die Intrinsic Size für den Platzhalter angeben damit es in der Vorschau gut aussieht:

![][image-1]

### Beispiel: Constraint

- Auch Constraints können eine Priority haben
- Hier allerdings nur ein einziger Wert (nicht separat für Hugging and Compression)

```swift
let myConstraint = self.heightAnchor.constraint(equalToConstant: 20)
myConstraint.isActive = true
myConstraint.priority = .init(500)
```



##  Gröse im Storyboard setzen

![][image-2]


## Default Werte
- 750 ist de Default Priority für **Content Compression Resistance**
- 250 ist die Default Priority für **Content Hugging**

- Das heisst: Die Elemente werden standartmässig gerne „gestreched“ aber ungerne „compressed“. 
- 1000 wäre „Required“

## Wie spielt das beim erstellen des Layouts eine Rolle?

Hier hat das die View weniger Platz zur Verfügung, als das sie eigentlich gemäss intrinsic content size haben möchte:

![][image-3]

Es findet also Compression statt. Entweder muss das Bild oder der Text komprimiert werden. Weil der Text eine geringere Compression Resistance hat, wird er komprimiert

![][image-4]

Die Grösse des Bildes bleibt die gleiche. Merke: Es gibt keine „Teilgewinner“.

## Quelle
- Empfehlenswerter Blogpost: [https://mischa-hildebrand.de/en/2017/11/the-auto-layout-comprehendium/][2]
## Zusammenfassung
- Begriff für "natürliche Grösse"
- Begriff für "wir stark will es nicht wachsen"
- Begriff für "wie stark will es nicht schrumpfen"
- Was sind die Default-Werte?

[1]:	ulysses://x-callback-url/open?id=QI0hpMFrXUpqEpjZRzsK1Q
[2]:	https://mischa-hildebrand.de/en/2017/11/the-auto-layout-comprehendium/

[image-1]:	assets/Bildschirmfoto%202021-09-11%20um%2012.56.52.png
[image-2]:	assets/Bildschirmfoto%202021-09-11%20um%2012.54.21.png
[image-3]:	assets/DraggedImage.tiff
[image-4]:	assets/DraggedImage-1.tiff

#learning unit#