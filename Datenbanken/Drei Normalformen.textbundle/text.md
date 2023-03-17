# Drei Normalformen
👆

## 1. Normalform

- Keine Strukturierte Daten in einem einzelnen Attribut

## 2. Normalform

> The Data depends on the (full) key
- Jedes Nichtschlüssel-Attribut muss von jedem Schlüsselkandidaten (= „full key“) voll abhängig sein.
- Bei Zusammengesetzten Schlüssel darf also nicht nur eine Abhängigkeit zu einem Teil des Schlüssels existieren
- In der Praxis oft: Logische Aufspaltung in Tabellen

Eine Tabelle ist anscheinend automatisch in der zweiten Normalform, wenn es nur einen Primärschlüssel gibt.

## 3. Normalform

> …and nothing but the key!
- Die Daten dürfen NUR vom Schlüssel abhängig sein, nicht nur transitiv über Umwege
- Hier wäre der Ort auch von der PLZ abhängig, was falsch ist
![][image-1]

## Zusammenfassung
- Welche drei Normalformen gibt es?

[image-1]:	assets/dritte_normalform_kundenbeispiel-409x61.jpg

#nur learning unit# #learning unit#