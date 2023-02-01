# Cloud Kit Grundlagen ☁️

## Übersicht

![][image-1]

- Jeder Record hat eine eindeutige ID
- Normalerweise kommen die Records in eine Default-Zone
- Während jeder Record einem Core Data Objekt entspricht, entspricht jede Zone einem Core Data Persistent Container

## Container / Zonen
- Jeder Applikation hat einen Container / Zone in der iCloud 
- Die Container / Zonen können auch zwischen mehreren Applikationen geteilt werden

## Public Datenbank
- Jeder Container enthält eine public Datenbank mit Informationen, welche für alle Nutzer zugänglich sind

## Private Datenbank
- Zudem kann jeder Nutzer eine private Datenbank haben: Hier verbrauchter Speicher wird der Storage des Users angerechnet

##  Quelle
Quelle: [https://www.answertopia.com/swiftui/an-overview-of-swiftui-core-data-and-cloudkit-storage/][1]


## Zusammenfassung
- Konzepte Verstehen: Container, Datenbank, Record

[1]:	https://www.answertopia.com/swiftui/an-overview-of-swiftui-core-data-and-cloudkit-storage/

[image-1]:	https://www.answertopia.com/wp-content/uploads/2022/04/word-image-14.jpeg