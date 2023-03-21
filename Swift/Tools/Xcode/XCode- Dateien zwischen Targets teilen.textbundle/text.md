# Xcode: Dateien zwischen Targets teilen
🤝

##  Datei
![][image-1]
##  CoreData
![][image-2]
##  Package
![][image-3]

## Problem

- Häufig hat ein File eine Abhängigkeit auf ein anderes File etc und so kopiert man schlussendlich das ganze Projekt in die Widget Extension

##  Lösung
- Um was zu verhindern, kann man mit Extensions arbeiten, so dass eine Grundversion des Files nicht zu viele Abhängigkeiten hat

##  Zusammenfassung
- Wie Teilt man eine Datei, ein CoreDataModel oder eine Library zwischen mehreren Targets?
- Wie wird verhindert, dass man den ganzen Abhängigkeitsbaum mitziehen muss?

[image-1]:	assets/DraggedImage.tiff
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-03-08%20um%2009.55.50.png
[image-3]:	assets/Bildschirm%C2%ADfoto%202023-03-08%20um%2010.06.30.png

#learning unit#