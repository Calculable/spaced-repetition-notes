# Unterschied Frame und Bounds und Alignment Rectangle
🖼️

##  Frame vs. Bounds

![][image-1]


##  Frame vs. Alignment Rectangle

Das Alignment Rectangle kann kleiner sein als das Frame. Man möchte zum Beispiel nicht, dass ein Schatten einen Einfluss auf das Alignment hat (UIKit berücksichtigt dies automatisch)

![][image-2]
(links: Ein Bild eines Kreises mit Schatten, Rechts ein Kreis und Schatten mit UIKit gezeichnet)

Die Intrinsic Content Size bezieht sich jeweils auf das Alignment Frame

Quelle: [https://www.vadimbulavin.com/view-auto-layout-life-cycle/][1]

## Zusammenfassung
- Frame vs. Bounds
- Frame vs. Alignment Rectangle

[1]:	https://www.vadimbulavin.com/view-auto-layout-life-cycle/

[image-1]:	assets/DraggedImage.tiff
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-05-02%20um%2017.38.51.png

#learning unit#