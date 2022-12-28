# Image
::7::

## Default-Verhalten
- Normalerweise haben Bilder immer ihre Orginalgrösse
 - Man kann es auch nicht mit Frame verändern. Hier sieht man am Pinken Rahmen, dass die Datei über das eigene Frame hinauswächst:

```swift
Image("Example")
    .frame(width: 300, height: 300) //funktioniert nicht wie gewünscht
```

## Clip
Man kann das ganze „clippen“, dann wird es aber beschnitten:

```swift
Image("Example")
    .frame(width: 300, height: 300)
    .clipped()
```

![][image-1]

##  Resize

Hier wird das Bild „gequetscht“

```swift
Image("Example")
    .resizable()
    .frame(width: 300, height: 300)
```

![][image-2]

Es gibt aber diverse Modifiiers, die man anwenden kann: 

```swift
.scaledToFit()
.scaledToFill()
....
```




[image-1]:	assets/Bildschirmfoto%202022-07-26%20um%2012.51.37.png
[image-2]:	assets/Bildschirmfoto%202022-07-26%20um%2012.52.03.png