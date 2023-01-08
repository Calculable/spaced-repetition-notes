# Positionierung 📍
::17.1::

##  Relative Positionierung

- Mit Offset-Modifier

```java
Text("Hello, world!")
    .offset(x: 100, y: 100)
```

## Absolute Positionierung

- Mit Position-Modifier

```java
Text("Hello, world!")
    .position(x: 100, y: 100)
```

Wenn man den `.position` Modifier verwendet, dann ist der Rückgabewert immer eine View, die den ganzen Verfügbaren platz einnimmt.

## Zusammenfassung
- Wie positioniert man eine View Absolut?
- Wie positioniert man eine View relativ?
- Was ist eine Auswirkung, wenn man es absolut positioniert?
