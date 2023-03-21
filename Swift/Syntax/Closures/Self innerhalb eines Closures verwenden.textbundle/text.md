# Self innerhalb eines Closures verwenden
👤

- Innerhalb eines Closures muss `self` immer angegeben werden.
- Statt `self` kann man auch `self?` angeben. 
- Somit ist man gezwungen darüber nachzudenken, ob man Strong oder Weak Capture verwerden will.
- Das Capturing geschieht implizit, man kann aber auch zum Beispiel Explizit `[weak self]` in die Capture List schreiben.
- Siehe auch Kapitel Capturing.

## Zusammenfassung
- Wie hat man aus einem Closure Zugriff auf `Self`

#learning unit#