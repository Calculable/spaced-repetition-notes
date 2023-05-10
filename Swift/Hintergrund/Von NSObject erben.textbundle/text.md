# Von NSObject erben
🕸️

## Was ist NSObject?
- Die Root-Klasse der meisten Objective-C Klassen

## Warum muss man manchmal von NSObject erben?
- Die Klasse wird mit dem Objective-C System kompatibel 
- =\> Runtime Flexibility
- z.B. benötigt für Key-Value Observing
- z.B: benötigt für NSCoding-Conformance


## NSObject und UIKit
- Alle UIKit Klassen erben am Ende von NSObject
- Man muss aber nicht selbst daran denken, das zu tun.

## Nachteile
- Schlechtere Performance


## Zusammenfassung
- Was ist NSObject?
- Warum muss man manchmal von NSObject erben? (Anwendungsfälle)
- NSObject und UIKit

#learning unit#