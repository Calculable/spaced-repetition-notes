# Lazy Variabeln können nicht in im SwiftUI Body verwendet werden
🦥

## Grund
- Weil lazy properties beim ersten Aufruf erzeugt werden, ist der Aufruf `mutating`
- Beim `body` in SwiftUI handelt es sich um ein Computet Property (also quasi um einen Getter)
- Und Getter dürfen nicht Mutable sein! 
- Es erscheint die Fehlermeldung: Cannot use mutating getter on immutable value: 'self' is immutable error

##  Workaround
 - Computed Properties verwenden

##  Zusammenfassung
Warum können Lazy Variabeln nicht im SwiftUI Body verwendet werden?

#nur learning unit#