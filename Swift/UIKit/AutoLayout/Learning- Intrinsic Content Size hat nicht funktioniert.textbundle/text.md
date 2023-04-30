# Learning: Intrinsic Content Size hat nicht funktioniert
📐

## Problem
In einem Codebeispiel habe ich ein UITextView verwendet, und wollte, dass dieses die Intrinsic Content Size einnimmt, allerdings hat die UITextView jeweils die Grösse eingenommen, die von aussen vorgeschlagen wurde.

## Begründung
- Eine UITextView hat keine Intrinsic Content Size und nimmt immer die vom Parent vorgeschlagene Dimension an.
- Stattdessen konnte ich ein Label verwenden, dass eine Intrinsic Content Size besitzt (die Grösse des Inhalts)

##  Zusammenfassung
- Begründung für das Problem


#learning unit#