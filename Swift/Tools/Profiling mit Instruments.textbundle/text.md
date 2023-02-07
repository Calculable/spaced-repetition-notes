# Profiling mit Instruments
⏲️

## Was kann man herausfinden?

### View Body

Wie oft wurde eine View neu gezeichnet und wie lange dauert es?


![][image-1]

### View Properties

Wie verändert sich der State der App?

> Sadly, Instruments isn’t (yet?) able to show us the exact property name there, which might be more confusing if you had several pieces of integer state being tracked.


###  Time Profiler

Wie lange dauern die einzelnen Funktionsaufrufe?

> To avoid clutter you might want to click the Call Tree button at the bottom, then choose Hide System Libraries. This will only show code that you wrote, however if your problem is that you were using the system libraries badly this might not help.

> To get straight to specific details, you can also click Call Tree and choose Invert Call Tree to flip things around so that leaf functions – those at the end of the tree – are shown at the top, and the disclosure indicators now let you drill down (drill up?) to the functions that called them.

### Core Animation Commits
Welche Re-Draws dauern besonders lange


## Code mit Instruments starten

`Cmd+I`

## Tipp

- Die genausten Resultate bekommt man auf einem richtigen Gerät statt dem Simulator

## Zusammenfassung
- Wie wird der Profiler gestartet (Shortcut)?
- Was zeigt der Profiler an?





[image-1]:	assets/how-to-use-instruments-to-profile-your-swiftui-code-and-identify-slow-layout-3.png

#nur learning unit#