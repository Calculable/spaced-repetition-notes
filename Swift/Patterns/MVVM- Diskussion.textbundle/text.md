# MVVM: Diskussion
🗯️

- Man muss es nicht zwingend einsetzen
- Man kann es auch bei einigen Views einsetzen und bei anderen nicht
- Es eignet sich vor allem, wenn man viele Funktionen hat, die eigentlich keine View-Aufgaben sind 
- Apple nennt MVVM nie direkt in der Dokumentation (sieh empfehlen kein bestimmtes Muster)
- Methoden und Properties, welche direkt mit dem View zu tun haben, sollen auch in der View bleiben. Auch Dinge wie `withAnimation` bleiben in der View.
- Ein grosser Nachteil ist, dass der `@FetchRequest`-Property-Wrapper nicht funktioniert. 
- =\> Egal ob man MVVM einsetzt oder nicht: Man sollte natürlich versuchen die Logik zu Kapseln. Das kann aber auch bedeuten einfach eine Funktion zu machen, die dann innerhalb des `body` property aufgerufen wird.


## Zusammenfassung
- Wie kann man MVVM pragmatisch einsetzen?
- Wie ist der offizielle Support für MVVM?
- Was sollte man tun, wenn man MVVM nicht einsetzt?

#nur learning unit#