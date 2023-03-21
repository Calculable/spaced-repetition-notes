# Reference Cycle auflösen
🔗

- Man sollte eine der beiden References `weak` machen.
- Dasjenige Objekt, dass weniger „ownership“ über das andere hat, sollte eine schwache Referenz halten.
- Wenn zum Beispiel der ViewController A den ViewController B präsentiert, dann hat A eine starke Referenz zu B und B eine schwache Referenz zu A
- Es spielt keine Rolle welches Objekt zuerst zerstört wird, sondern die Beziehungen zwischen den Objekten ist ausschlaggebend.

##  Zusammenfassung

- Wer enthält die strong und wer die weak Reference?
- Was für eine Rolle spielt die Reihenfolge, in der die Objekte zerstört werden?

#learning unit#