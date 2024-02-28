# Wozu ist die Intrinsic Content Size gut?
↔️
- Die natürliche Höhe und Breite einer View
- Autolayout muss von einer View X, Y, Höhe und Breite kennen
- Durch die Intrinsic Content Size braucht man weniger Constraints
	- Beispiel: \> „place this button 20 points from the top and center it horizontally” and that’s enough“
- Das System erzeugt automatisch einen optionalen Constraint für die intrinsic content Size - **Das ist ein sehr hilfreiches mentales Model **
	- Das bedeutet auch: Wenn man einen eigene Constraints setzt kann die Intrinsic Content Size ignoriert werden, wenn man das möchte
	- Genau genommen sind es zwei Constraints

![][image-1]
(Quelle: [https://mischa-hildebrand.de/en/2017/11/the-auto-layout-comprehendium/][1])

**- Die  Priorität dieser System-Constraints kann mit Content Hugging und Compression Resistance gesteuert werden**
## Beispiele

|                  |              | Intrinsic Content Size?                                                 |
| ---------------- | ------------ | ----------------------------------------------------------------------- |
| UISwitch         | ![][image-2] | Ja                                                                      |
| UIButton         | ![][image-3] | Ja, Anhand des Labels                                                   |
| UIImageView      | ![][image-4] | Ja, Grösse des Bildes                                                   |
| UILabel          | ![][image-5] | Ja, Grösse des Textes (auf einer Zeile wenn Breite nicht eingeschränkt) |
| Beliebige UIView |              | Nein                                                                    |

##  Quellen

Quelle: [https://www.hackingwithswift.com/example-code/uikit/what-is-a-views-intrinsic-content-size][2]

[https://mischa-hildebrand.de/en/2017/11/the-auto-layout-comprehendium/][3]

##  Learning Unit
- Was macht das System bei einer View, welche eine Intrinsic Content Size hat?

[1]:	https://mischa-hildebrand.de/en/2017/11/the-auto-layout-comprehendium/
[2]:	https://www.hackingwithswift.com/example-code/uikit/what-is-a-views-intrinsic-content-size
[3]:	https://mischa-hildebrand.de/en/2017/11/the-auto-layout-comprehendium/

[image-1]:	https://mischa-hildebrand.de/wordpress/wp-content/uploads/2017/10/Intrinsic-Content-Size-For-Real-400x279@2x.png
[image-2]:	https://mischa-hildebrand.de/wordpress/wp-content/uploads/2017/10/UISwitch.png
[image-3]:	https://mischa-hildebrand.de/wordpress/wp-content/uploads/2017/10/UIButton.png
[image-4]:	https://mischa-hildebrand.de/wordpress/wp-content/uploads/2017/10/UIImageView.png
[image-5]:	https://mischa-hildebrand.de/wordpress/wp-content/uploads/2017/10/UILabel.png

#learning unit#