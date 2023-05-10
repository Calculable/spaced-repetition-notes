#  IBOutlet: Strong or Weak References?
💪

## Argumente für „weak“
- Man vermeidet teilweise Retain Cycles die einem nicht bewusst sind
- Man sieht sehr häufig code, wo es „weak“ ist

## Argumente für „strong“
- Von Apple empfohlen
- Ausnahme: Eine Custom View hat wiederum eine „strong“ Referenz auf etwas höheres in der Hierarchie (was generell eine schlechte Idee ist)
 - Macht semantisch mehr sinn, den es handelt sich ja um eine „Ownership “

##  Zusammenfassung
- Empfehlung von Apple
- Was spricht dafür?
- Was dagegen?

#learning unit#