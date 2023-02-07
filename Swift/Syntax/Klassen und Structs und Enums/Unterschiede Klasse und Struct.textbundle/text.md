# Unterschiede Klasse und Struct
🎭

##  Klassen

- Können Vererbung verwenden
- Haben keinen Default Initializer
- Klassen werden als Referenz weitergegeben
- Können Deinitializers haben
- Bei Konstanten Klassen kann man trotzdem die Variabeln verändern

##  Structs

- Können keine Vererbung verwenden
- Haben automatisch einen membervise initializer
- Structs werden als Kopie weitergegeben
- Können keine Deinitializers haben
- Bei Konstanten Structs kann man die Variabeln nicht verändern.

Beachte: Auch Arrays sind Value Types!

## Zusammenfassung
Unterschiede: Vererbung, Initializer, Referenz, Konstanten