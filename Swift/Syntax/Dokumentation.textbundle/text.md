# Dokumentation
📝

# Code Dokumentieren: Ergänzungen

## Dokumentation auf einer Zeile (DocC)

Mit drei Schrägstrichen

```
///Text zur Begrüssung
var greeting = "Hello World"
```

## Dokumentation auf mehreren Zeilen (DocC)

Mit drei Schrägstrichen

```
/**
Text zur Begrüssung
*/
var greeting = "Hello World"
```

## Dokumentations-Vorlage

Kann generiert werden:

```
/// Description
/// - Parameters:
/// 	- fileName: xy
///	- Returns: xy
```

## Markdown Syntax, Summary und Diskussion

Beachte: Der erste Absatz wird immer automatisch als "Summary" angezeigt. Alles darunter wird unter Diskussion aufgeführt

````
/// Kurze Beschreibung der Funktion
///
/// Diskussion
///
/// # Hinweis
/// Hinweise
///
/// # Verwendung
/// ```
/// let xy = 5
/// ```
/// - Listeneintrag
````

Titel mit `#` werden gleichwertig wie das Summary oder die Diskussion angezeigt.

## Links
> If you’re using Xcode 13 or later, you can use double backticks to produce links inside DocC documentation, like this:

```markdown
Make sure and avoid using ``badFunction()`` unless you enjoy problems.
```


## Zusammenfassung
- Wie schreibt man die Dokumentation auf mehreren / auf einer einzelnen Zeile?
- Wie sieht die generierte Vorlage aus?
- Wie kann Markdown verwendet werden?
- Wie kann man Inhalte in den "Summary" bzw. den "Discussion"-Abschnitt hinzufügen?
- Wie macht man einen Link