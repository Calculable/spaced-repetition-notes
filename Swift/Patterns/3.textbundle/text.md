
# Viper 🏛️

## Einordnung
- Architekturpattern, ähnlich wie MVC und MVVM
- Nicht geeignet wenn die Anforderungen häufig ändern.
- Für grössere Projekte

##  Übersicht / Rollen
![][image-1]

## Erklärung der Rollen
- **View**: Darstellung. Informiert den Presenter wenn etwas geschieht.
- **Presenter**: Die wichtigste Komponente. „Verkehrspolizist“. Wird über UI eingaben informiert. Nur diese Klasse kann mit dem Rest des Systems kommunizieren. Aktualisiert das UI. Kann mit den anderen Komponenten kommunizieren.
- **Interactor**: Business Logik (z.B. Network Calls)
- **Entity**: Enthält die Daten (Model)
- **Router**: Kümmert sich um die Navigation. Hört auf den Presenter wann was angezeigt werden soll

## Bedeutung von Protokollen

Zwischen den Schnittstellen definiert man Protokolle. Für unterschiedliche Module hängt man jeweils noch den Modulname vorne an.

> Viper is a delegation-driven architecture. So, most of the communication between different layers executes through delegation. One layer calls another through a protocol.

##  Zusammenfassung
- Rollen
- Zusammenspiel
- Bedeutung von Protokollen

[image-1]:	https://miro.medium.com/max/1400/1*-Mfew6qvLQ-t-DSOkY23Aw.webp