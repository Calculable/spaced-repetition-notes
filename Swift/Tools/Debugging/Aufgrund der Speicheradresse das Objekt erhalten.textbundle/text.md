# Aufgrund der Speicheradresse das Objekt erhalten
💾

=\> Das ist sehr hilfreich für das Debugging!

Beispiel: Ich habe diese Image View:

```swift
<UIImageView: 0x12eb0c680; frame = (0 0; 44 44); opaque = NO; autoresize = W+H; userInteractionEnabled = NO; tintColor = <UIDynamicProviderColor: 0x60000038ccc0; provider = <__NSMallocBlock__: 0x600000dcfc30>>; image = <UIImage:0x600003002760 CGImage "TabbarShop"; (24 24)@3>; layer = <CALayer: 0x600000388800>>
```
(Zum Beispiel beim Layout-Debugging erhalten)

Jetzt kann man so darauf zugreifen:
![][image-1]

![][image-2]

##  Zusammenfassung
- Wie muss die Expression aussehen wenn man die Speicheradresse hat?

[image-1]:	assets/Bildschirmfoto%202023-09-21%20um%2007.40.20.png
[image-2]:	assets/Bildschirmfoto%202023-09-21%20um%2007.41.03.png

#learning unit#