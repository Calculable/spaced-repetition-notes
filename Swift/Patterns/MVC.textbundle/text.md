
# MVC
🏛️

## Pattern

![][image-1]

## Einordnung UIKit

=\> hier passt das Pattern gut

- Model: Einfaches Datenmodel
- Controller: View Controller
- View: z.B. Storyboard

##  Einordnung SwiftUI

=\> Hier passt das Pattern nicht so gut. Man setzt eher auf MVVM

> Although our SwiftUI layouts conform to the View protocol, if you were to try to think about them in MVC terms I’d say they were more like  _controllers_.

=\> Denn wir Beschreiben ja nur die Views. Das heisst die eigentliche View, ist der Part im Hintergrund von SwiftUI der es Rendert.

Wenn man nicht MVVM einsetzt hat man also auch eine MVC-Architektur mit, wobei unser „View“ eigentlich der Controller ist und der Render-Part von SwiftUI eigentlich die View ist.

##  Zusammenfassung
- Rollen / Zusammenspiel
- Einordnung: UIKit und SwiftUI

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-01-02%20um%2013.41.40.png

#nur learning unit#