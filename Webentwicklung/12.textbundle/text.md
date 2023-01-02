# CSS Grössenangaben ↕️

## Relative Grössenangaben

```java
font-size: 2em;   /* multiples of element's original font-size */
font-size: 2rem;  /* or the root element's font-size */
font-size: 2vw;   /* multiples of 1% of the viewport's width (CSS 3) */
font-size: 2vh;   /* or its height */
font-size: 2vmin; /* whichever of a vh or a vw is smaller */
font-size: 2vmax; /* or greater */
```

## Absolute Grössenangaben

```java
width: 200px;     /* pixels */
font-size: 20pt;  /* points */
width: 5cm;       /* centimeters */
min-width: 50mm;  /* millimeters */
max-width: 5in;   /* inches */
```

## Zusammenfassung
- Relativ zur Orginal-Schriftgrösse
- Relativ zur Orginal-Schriftgrösse des Parent
- Relativ zum Viewport
- Pixel, Punkte, Cm etc.
