# Date Formatter
📅

## Drei Varianten

- **Variante 1**: DateFormatter mit explizitem `.dateFormat` (zum Beispiel "dd/MM/yyyy"). Nicht empfohlen, weil jedes Land ein anderes Date Format haben sollte.

- **Variante 2**: Formatter mit `.locale` und `.dateStyle` (z.B. "long") - gut für die Ausgabe auf dem UI. Wenn man will kann man auch genauere Konfigurationen vornehmen

- **Variante 3**: `ISO8601DateFormatter()` verwenden. Vor allem für die Fälle, wo man Dates an ein anderes Computersystem weitergeben muss.

=\> Mit iOS 16 kann man auch direkt das Datum formatieren. Siehe Kapitel „Date Formatter: Details“


## Details

Siehe Zusammenfassung ["Date Formatter Details"][1]: 

## Zusammenfassung

- Drei Varianten, um Dates zu formatieren (nur Konzept, Einordnung)
- Wie heisst der internationale ISO-Standard für Dates?

[1]:	ulysses://x-callback-url/open?id=tEIz2DVcLaFPofUzGd3r9g

#learning unit#