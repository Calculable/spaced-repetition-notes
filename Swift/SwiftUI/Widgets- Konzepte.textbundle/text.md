# Widgets: Konzepte
🖲️

## Allgemeine Hinweise
- Zwingend Swift UI
- Widgets sind ein eigenes Target innerhalb des Projekts
- Es gibt verschiedene Grössenklassen 
- Über Links kann man zurück in die Haupt-Applikation linken

## 4 benötigte Komponenten
- `TimelineEntry` für das Datenmodell. Einzige Anforderung: ein Property `date`
- `TimelineProvider`: Stellt ein oder mehrere `TimelineEntries` zur Verfügung und gibt an, wann das System das nächste mal eine Anfrage stellen soll.
- `View`: Rendert ein `TimelineEntry`
- `Widget`: Verknüpft `TimelineProvider` mit der `View`

## Zusammenfassung
- Welche 4 Komponenten gibt es und was ist deren Aufgabe?




#nur learning unit#