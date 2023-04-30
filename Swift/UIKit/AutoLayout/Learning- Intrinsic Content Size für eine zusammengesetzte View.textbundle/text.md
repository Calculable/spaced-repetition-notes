# Learning: Intrinsic Content Size für eine zusammengesetzte View
↕️

## Problem

- Ich wollte dass eine Custom View seine Intrinsic Content Size einnimmt
- Allerdings wurde immer die von aussen vorgeschlagene Grösse verwendet:

![][image-1]

##  Erklärung

- Die View wusste nicht wie hoch sie sein soll, weil es keinen entsprechenden Contraint gibt
- Ich dachte, ich darf keinen Bottom-Constraint setzen, weil ansonsten die Intrinsic Content Size nicht funktioniert
	- Aber das Gegenteil ist der Fall: Nur dank dem Bottom Constraint weiss die View, wie gross sie sein darf

## Lösung

![][image-2]

## Zusammenfassung
- Was ist die Erklärung und Lösung?

[image-1]:	assets/DraggedImage.png
[image-2]:	assets/DraggedImage-1.png

#learning unit#