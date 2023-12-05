# ViewController: ViewIsAppearing
🌅

## Wann wird es aufgerufen?
- Für View Controller
- Nachdem die View bereits zur Hierarchie hinzugefügt wurde (anders wie bei viewWillAppear)

## Welche Infos hat man zusätzlich im Vergleich zu viewWillAppear?
- Trait Collection ist aktuell (Neu erben die View Controller die Trait Collection von der Superview ihrer View, früher war das anderst)
- View Geometrie ist aktuell

## Kompatibilität
- Ein neues Callback seit iOS 17
- Rückwärtskompatibel mit iOS 13

##  Zusammenfassung
- Wann wird es aufgerufen
- Welche Infos hat man zusätzlich im Vergleich zu viewWillAppear?


#learning unit#