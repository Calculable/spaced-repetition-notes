# .fixedSize() Modifier
↕️

## Verhalten
Mit `fixedSize()` ignoriert eine View die vorgeschlagene Grösse das Parents  

Man kann es auch noch einschränken:

```swift
.fixedSize(horizontal: false, vertical: true)
```

=\> Wenn von aussen ein Frame definiert wird, dann wird das einfach ignoriert

## Beispiel

Rot ist das Frame und Blau hat den `fixedSize()` modifier auf dem Text gesetzt.

![][image-1]

##  Häufiger Anwendungsfall: Container Views


- Oft wird die Option auf Container Views gesetzt.
- Hier hat man einen HStack mit Buttons:

![][image-2]

Wenn man jetzt die Option `.frame(maxWidth: .infinity)` auf den Kindern setzt erhält man folgendes - der HStack nimmt ebenfalls die gesamte Grösse ein:

![][image-3]

Wenn man jetzt allerdings `fixedSize()` auf dem VStack anwendet, dann orientiert sich die Grösse wieder am Inhalt der Buttons:

![][image-4]

Was geschieht: Man hat die Elemente in einem Container mit der kleinsmöglichen Grösser. Die Elemente selbst nehmen im Container dann die maximale Verfügbare grösse ein

## Zusammenfassung
- Wozu braucht man den `fixedSize()` modifier?
- Wie funktioniert der häufige Anwendungsfall mit den Containern?

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-05-17%20um%2009.46.14.png
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-05-17%20um%2009.50.31.png
[image-3]:	assets/Bildschirm%C2%ADfoto%202023-05-17%20um%2009.56.06.png
[image-4]:	assets/Bildschirm%C2%ADfoto%202023-05-17%20um%2009.54.54.png

#learning unit#