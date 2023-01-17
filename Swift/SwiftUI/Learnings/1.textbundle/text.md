# Learning: @State mit Array


## Problem
- Wenn ich ein Array als `@State` beobachte, dann sehe ich die Veränderungen des Arrays (hinzufügen von Elementen, entfernen von Elementen), aber nicht wenn sich die einzelnen Elemente verändern. 
- Beachte: Ein Array ist ein Struct und muss also mit `@State` beobachtet werden.

## Lösung 1
- Meistens verwende ich in der View `ForEach`, um durch den Array zu loopen
- Ich könnte die View also aufsplitten und eine weitere View machen, in der nur die Details eines einzelnen Elements angezeigt werden.

## Lösung 2
- Ich könnte eine Wrapper-Klasse um das Array machen.
- Statt anschliessend die einzelnen Elemente direkt zu manipulieren, erstelle ich helper-Methoden in der Wrapper-Klasse (so wurde es bei Remember gemacht)
- Die Wrapper-Klasse ist ein `ObservableObject` und jedes mal wenn eine Funktion aufgerufen wird, welche ein Element im Array verändert, ruft man `objectWillChange` auf

## Zusammenfassung
- Was ist das Problem
- Welche zwei Lösungen habe ich gefunden?

#nur learning unit#