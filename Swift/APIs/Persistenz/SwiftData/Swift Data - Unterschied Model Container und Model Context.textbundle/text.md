# Swift Data - Unterschied Model Container und Model Context
💽

## Übersicht

![][image-1]

- Der Container kann einer View mitgegeben werden und ist dann für alle Views verfügbar
- Der Container kann definieren wie die Objekte gespeichert werden (Cloud, Phone SSD, Temporärer speicher)

So wird ein Container zur View hinzugefügt:

```swift
.modelContainer(for: YourModel.self)
```

Dabei wird automatisch auch ein Kontext erzeugt (der automatisch auf dem Main Actor läuft) 


## Zusammenfassung
- Was macht der Model Context?
- Was macht der Model Container?

[image-1]:	assets/context-und-container.png

#learning unit# #Container und Context# #guide