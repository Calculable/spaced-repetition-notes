# SOLID Principles
👌

## Single Responsibility Principle
- Jede Klasse sollte nur eine Aufgabe haben

## Open-Closed Principle
- Es sollte einfach sein, neue Features zur Klasse hinzuzufügen
- In der Praxis heisst das oft: Mit Generics arbeiten
- z.B. statt einer Klasse `UserFetcher` schreibt man ein `Fetcher<T>`

## Liskov Substitution Principle
- LSP besagt, dass eine Funktion die für eine Klasse funktioniert, auch für deren Unterklassen funktionieren soll
- In der Praxis: Manuelle Prüfungen der Klasse (`if XY is MyClass`) vermeiden

## Interface Segregation Principle
- Statt ein grosses Interface sollte man besser mehrere kleine Interfaces machen
- In der Praxis: Deshalb gibt es zum Beispiel neben `Codable` auch `Encodable` und `Decodable`

## Dependency Inversion Principle

- High-Level Code (zum Beispiel ViewController) sollte nicht direkt auf Low-Level Code zugreifen (z.B. Networking)
- Stattdessen verwendet man Protokolle
- Nicht verwechseln mit Inversion of Control

## Zusammenfassung
- Was bedeuten die 5 Prinzipien

#learning unit#