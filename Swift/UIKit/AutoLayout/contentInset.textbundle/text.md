# contentInset
📜

- Definiert die Distanz wie weit von der Safe Area bzw. den Kanten der Scroll View der Inhalt anfangen soll:

![][image-1]

Beachte: Wenn man zu scrollen beginnt, geht der Inhalt der Scroll View dahinter:

![][image-2]

- Standart: 0
- Es bezieht sich nur auf die **zusätzliche** Distanz zur Safe Area

## Zusammenhängend

-  **adjustedContentInset**: Readonly. Dieser Wert beinhaltet den gesamten Inset (also safeAreaInsets + den zusätzlichen eigenen contentInset)
- **func adjustedContentInsetDidChange()**: Damit kann man informiert werden, wen sich an den Content Insets etwas verändert
- **contentInsetAdjustmentBehavior**: Damit steuert man, wie die Safe-Area berücksichtigt wird

=\> In den meisten Föllen könnte man also auch einfach die Safe Area anpassen.

## Zusammenfassung
- Was wird mit diesem Property gesteuert?
- Inwiefern spielt die Safe Area hier eine Rolle?

[image-1]:	assets/Unbenanntes%20Diagramm.drawio.png
[image-2]:	assets/Unbenanntes%20Diagramm.drawio_2.png

#learning unit#