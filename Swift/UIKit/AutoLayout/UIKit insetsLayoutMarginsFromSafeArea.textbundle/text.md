# UIKit insetsLayoutMarginsFromSafeArea
🖼️

##  Standartmässig berücksichtigen Layout Margins die Safe Area

Das View-Property `insetsLayoutMarginsFromSafeArea` ist standartmässig auf true. Das heisst, das System kann die Margins also vergrössern damit kein Inhalt ausserhalb der safe area liegt

Das wäre der standartmässig Layout-Margins guide:

![][image-1]

Wenn man hingegen `insetsLayoutMarginsFromSafeArea` bei der Superview auf false setzt, dann wäre es:

![][image-2]

##  Zusammenfassung
- Was macht das Property?

[image-1]:	assets/simulator_screenshot_7D5AEEB6-CE42-4F7D-9039-C14A79706210.png
[image-2]:	assets/simulator_screenshot_F3205449-96DD-4E45-AD4F-EEA7142AA551.png

#learning unit#