# SwiftUI Identify
👤
## Warum muss man bei SwiftUI oft einen `id` Parameter angeben, zum Beispiel bei Loops

- Swift UI kann nicht wissen, ob zwei Dinge „das gleiche“ sind - das ist eine Fachliche Frage.
- Über eine ID kann man der App mitteilen, dass zwei Objekte gleich sind oder zwei unterschiedliche Objekte (zum Beispiel zwei Personen mit gleichem Namen)
- So weiss SwiftUI wie der Übergang zwischen diesen beiden Elementen aussehen soll

> Identity is how SwiftUI recognizes elements as the same or distinct across multiple updates of your app.

##  Typ 1: Explicit Identity

- In UIKit und App Kit gibt es Pointer Identity
- Bei SwiftUI wird das nicht verwendet

So ist zum Beispiel eine solche Animation möglich, auch wenn die Elemente zwischen zwei Verschiedenen Views wechseln:

![][image-1]

## Typ 2: Structural Identity

- Jede View hat eine Identität, auch wenn wir keine explizite Identität angeben
- Dann spricht man von Structural identity
- Diese wird automatisch aus der Stuktur der View Hierarchie generiert

![][image-2]



##  Zusammenfassung
-  Warum muss man bei SwiftUI oft einen `id` Parameter angeben, zum Beispiel bei Loops
- Was ist Explicit Identity?
- Was ist Structural Identity?





[image-1]:	assets/2023-07-10%2020.21.34.gif
[image-2]:	assets/Bildschirmfoto%202023-07-10%20um%2020.25.08.png

#learning unit#