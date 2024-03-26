# .fixedSize() Modifier
↕️

## Verhalten
Mit `fixedSize()` ignoriert eine View die vorgeschlagene Grösse das Parents:


![][image-1]![][image-2]

Siehe: [https://www.swiftuifieldguide.com/layout/padding/][1]

  

Man kann es auch noch einschränken:

```swift
.fixedSize(horizontal: false, vertical: true)
```

=\> Wenn von aussen ein Frame definiert wird, dann wird das einfach ignoriert

## Beispiel

Rot ist das Frame und Blau hat den `fixedSize()` modifier auf dem Text gesetzt.

![][image-3]

##  Häufiger Anwendungsfall: Container Views


- Oft wird die Option auf Container Views gesetzt.
- Hier hat man einen HStack mit Buttons:

![][image-4]

Wenn man jetzt die Option `.frame(maxWidth: .infinity)` auf den Kindern setzt erhält man folgendes - der HStack nimmt ebenfalls die gesamte Grösse ein:

![][image-5]

Wenn man jetzt allerdings `fixedSize()` auf dem VStack anwendet, dann orientiert sich die Grösse wieder am Inhalt der Buttons:

![][image-6]

Was geschieht: Man hat die Elemente in einem Container mit der kleinsmöglichen Grösser. Die Elemente selbst nehmen im Container dann die maximale Verfügbare grösse ein

## Zusammenfassung
- Wozu braucht man den `fixedSize()` modifier?
- Wie funktioniert der häufige Anwendungsfall mit den Containern?

[1]:	https://www.swiftuifieldguide.com/layout/padding/

[image-1]:	assets/Bildschirmfoto%202024-03-23%20um%2007.49.33.png
[image-2]:	assets/Bildschirmfoto%202024-03-23%20um%2007.49.42.png
[image-3]:	assets/Bildschirm%C2%ADfoto%202023-05-17%20um%2009.46.14.png
[image-4]:	assets/Bildschirm%C2%ADfoto%202023-05-17%20um%2009.50.31.png
[image-5]:	assets/Bildschirm%C2%ADfoto%202023-05-17%20um%2009.56.06.png
[image-6]:	assets/Bildschirm%C2%ADfoto%202023-05-17%20um%2009.54.54.png

#learning unit#