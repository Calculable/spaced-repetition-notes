# Memory Leaks Debuggen

## Visual Memory Debugger starten

Der Visual Memory Graph Debugger kann bei laufender App hier gestartet werden:

![][image-1]

##  Aufbau
- Auf der linken Seite findet sieht man die Instanzen, die sich im Heap befinden
- Im Hauptfenster sieht man den Memory Graph
	- Dicke Linien sind starke Referenzen
	- Leichte Linien sind unbekannte Referenzen (weak oder strong)


![][image-2]

- Wenn man auf eine Instanz klickt, sieht man alle starken Referenzen welche auf die Instanz zeigen
- Leider sieht man nicht mit einem Klick welche Referenzen ein Objekt hält

## View aufgeräumter anzeigen

Wenn man die Option Malloc Stack einschaltet, ist das Resultat etwas aufgeräumter:

![][image-3]

Mit Malloc Scribble wird jedes mal, wenn man Memory freigibt, wird es mit 0x55 überschrieben, damit man keine „Accidental Storage of Data“ hat:

![][image-4]

## Automatische Erkennung
- Einfache Memory Leaks werden vom Memory Debugger automatisch erkannt:

![][image-5]![][image-6]

- Achtung: Die Automatische Erkennung funktioniert nicht in allen Fällen!


## Häufiges Indiz für Memory Leaks
- Beispiel: Jedes mal wenn man einen bestimmten View-Controller anzeigt hat man eine zusätzliche Instanz davon im Heap:

![][image-7]


##  Leaks mit Instruments untersuchen
Man kann die Leaks auch mit Instruments untersuchen:

![][image-8]![][image-9]

=\> Um den Memory Graph zu sehen braucht man jedoch wieder Xcode


## Memory Report

Auch hier kann es auffallen, dass zum Beispiel die Memory Usage nicht zurückgeht obwohl zum Beispiel ein View Controller verworfen wurde:

![][image-10]
Achtung: Das ist nicht wirklich zuverlässig

[image-1]:	assets/001.png
[image-2]:	assets/Bildschirmfoto%202024-03-01%20um%2007.11.34.png
[image-3]:	assets/Bildschirm%C2%ADfoto%202023-04-05%20um%2021.57.08.png
[image-4]:	assets/Bildschirm%C2%ADfoto%202023-04-05%20um%2021.57.45.png
[image-5]:	assets/Bildschirmfoto%202024-03-01%20um%2007.21.28.png
[image-6]:	assets/Bildschirmfoto%202024-03-01%20um%2007.21.48.png
[image-7]:	https://doordash.engineering/wp-content/uploads/2019/05/Screen-Shot-2019-05-04-at-3.51.25-PM.png
[image-8]:	assets/Bildschirmfoto%202024-03-01%20um%2007.41.22.png
[image-9]:	assets/Bildschirmfoto%202024-03-01%20um%2007.42.33.png
[image-10]:	assets/Bildschirmfoto%202024-03-01%20um%2007.45.24.png

#guide