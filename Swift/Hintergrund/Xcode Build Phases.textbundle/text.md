# Xcode Build Phases
🧩

## Build Phasen definieren
Für jedes Target kann man Build-Phasen definieren:
![][image-1]

## Target Dependencies
- Xcode prüft ob das Projekt Dependencies hat. Falls ja werden diese zuerst kompiliert

## Compile

- Input: Source Code (.swift, .m)
- Output: Object File (.o)

- **Begriff Object File**: Kompilierte mehrere Codefragmente.  Der Linker setzt diese Files dann zusammen.
- **Begriff Symbol:** Referenziert ein Codefragment (zum Beispiel Function Call)

![][image-2]
## Link
- **Input**: Object Files (.o)
- **Output**: Executable oder Library



## Copy resources

Resourcen (Asset Kataloge, Storyboards, …) werden in das App Bundle kopiert
![][image-3]

## Custom Scrips

Man kann auch eigene Skripts hinzufügen:

![][image-4]

- Zum Beispiel für Code Generation etc.

##  Zusammenfassung
- Kompilieren (Input / Output)?
- Linken (Input / Output)?

[image-1]:	assets/Bildschirmfoto%202023-07-27%20um%2011.51.45.png
[image-2]:	assets/Bildschirmfoto%202023-07-27%20um%2012.01.41.png
[image-3]:	assets/Bildschirmfoto%202023-07-27%20um%2012.01.59.png
[image-4]:	assets/Bildschirmfoto%202023-07-27%20um%2011.50.35.png

#learning unit#