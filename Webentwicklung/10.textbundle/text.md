# CSS Selektoren 👆

## Mehrere Klassen
```java
.class1.class2 { }
```

## Bestimmtes Attribut

```java
[attr] { font-size:smaller; }
[attr='value'] { font-size:smaller; }
```

## Kinder

```java
/* Direkte Kinder */
div.some-parent > .class-name { }

/* Auch tiefer in der Hierarchie erlaubt */
div.some-parent .class-name { }
```

## Angrenzende Geschwister
```java
.i-am-just-before + .this-element { }
```

##  Pseudoklassen
```java
selector:hover { }
```

## Zusammenfassung
- Mehrere Klassen
- Bestimmtes Attribut
- Kinder (direkt und Indirekt)
- Angrenzende Geschwister
- Pseudoklassen