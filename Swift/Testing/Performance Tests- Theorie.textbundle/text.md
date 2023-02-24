# Performance Tests: Theorie
🏎️

## Wie funktionieren Performance Tests?

- XCode trackt die Resultate über die Zeit
- Wenn der Code mit der Zeit signifikant schlechter wird, wird ein Fehler angezeigt (Der Code darf sich in einer Standartabweichung von 10% bewegen)
- Der Test wird 10 mal wiederholt und der Durchschnitt berechnet, damit Schwankungen ausgeglichen werden


## Allenfalls ein neues Test-Target erstellen

- Wenn man viele Performance-Tests hat, sollte man ein eigenes Test-Target erstellen (nur nur eine eigene Klasse)


## Baseline festlegen

- Wenn man den Code speichert, hat man neben dem Text ein Diamanten-Symbol.
- Nach einem Testdurchlauf kann man auf den Diamant klicken und auf "Set Baseline"

## Testumgebung

- Man sollte die Performance-Tests jeweils in der gleichen Umgebung testen, da es sonst zu starken Abweichungen kommt und die Tests fehlschlagen.

## Zusammenfassung
- Wann bezeichnet XCode einen Performance-Test als "failed"?


#nur learning unit#