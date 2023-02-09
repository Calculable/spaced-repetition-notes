# Core Data: Mit Optionals umgehen
📟

## Problem
- In Core Data sind (fast) alle erzeugten Properties Optionals, selbst wenn es im Datenmodell anders angegeben ist (Grund: zu Objective-C Zeiten haben Optionals ganz anders funktioniert)

##  Lösung 1 (nicht empfohlen)

- Bei der Entität kann man die Auswahl bei Codegen auf Manual/None stellen:
![][image-1]


- Anschliessend kann man den Code für die Entität erzeugen:
![][image-2]

- Für jede Entität werden zwei Klassen erzeugt: In einem File stehen die ganzen Properties und im anderen File können wir Ergänzungen machen.
- Der Vorteil dass es zwei Dateien sind: Die Datei mit den Properties kann man immer wieder neu erzeugen, wenn sich etwas im Datenmodell verändert hat.
- In dieser Lösung wird dieses File jedoch angepasst, um aus den Optional-Properties Required-Properties zu machen:

```swift
@NSManaged public var color: String?
//wird zu
@NSManaged public var color: String
```

- Das ist jedoch nicht ideal, weil man dadurch die Möglichkeit verliert, das generierte Code-Modell bei Änderungen des Core-Data-Modells automatisch zu aktualisieren!
- Übrigens: Auch die Annotation `@NSManagedObject` ist kein Property wrapper, sondern damit sagt man, dass sich Core Data um die Verwaltung dieses Attributs kümmert

## Lösung 2

Man generiert aus dem Model KEIN Code-File. Stattdessen schreibt man eine Extension:

```swift
extension LearningUnitCollection {
     public var wrappedTitle: String {
         title ?? "Unknown Title"
     }
}
```

Nachteil hier: Man kann die Wrapper-Methoden natürlich einfach umgehen, muss also daran denken, diese auch zu verwenden.

## Zusammenfassung
- Welche zwei Lösungen gibt es, um mit der Optionalität in Core Data umzugehen?

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-02-09%20um%2006.43.17.png
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-02-09%20um%2006.43.38.png