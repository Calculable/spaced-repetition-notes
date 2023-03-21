# Array: Behind the Scenes
📚

## Schneller Zugriff mit Index
- Die Elemente liegen alle nebeneinander im Speicher
- Weil abgelegten Typen alle die gleiche Grösse haben, ist der Zugriff über den Index sehr schnell (weil sich die Speicheradresse berechnen lässt)
	- Hinweis: Wenn die abgelegten Typen keine Structs sind, dann ist ja im Array nur die Speicheradresse enthalten, was ja auch immer die gleiche Grösse hat.
- Zugriff mittels Index nennt sich **RandomAccess**

## Nachteil
- Nachteil: Wenn man ein Element entfernt, müssen alle nachfolgenden verschoben werden

## Zusammenfassung
- Warum ist der Zugriff mittels Index so schnell?
- Was ist der Nachteil


#learning unit#