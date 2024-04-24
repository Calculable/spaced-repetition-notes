# UIView: layoutSubviews()
🧩

## Zweck

- Wird aufgerufen, wenn die Child-Views neu positioniert werden müssen (idr. weil sich das Frame verändert hat oder weil child-views hinzugefügt oder entfernt wurden)
- Primär für Manuelle Layouts. Die eigene Grösse ist bekannt und jetzt kann man hier die Child-Views positionieren
- Dies geschieht **Top-Down ** (zuerst Superview und dann subview)
- Für UIController gibt es hingegen `viewWillLayoutSubviews` und `viewDidLayoutSubviews`
- Meistens muss man das nicht anpassen, ausser man hat sehr komplexe UI's so dass Standart Constraints nicht mehr ausreichen

## Beispiel

- Man möchte zum Beispiel einen Corner-Radius von der View-Grösse abhängig machen:

```swift
override func layoutSubviews() {
    super.layoutSubviews()
    containerView.layer.masksToBounds = true
    containerView.layer.cornerRadius = 0.5 * containerView.bounds.width
	amotherView.frame = ...
}
```

- `super.layoutSubviews()` nicht vergessen!

## Was sollte man hier nicht aufrufen?

- Hier sollte man keine Constraints der View ausserhalb der aktuellen Hierarchie bearbeiten.
	- Dies ist nicht der Ort, wo man generell Constraints definieren sollte. =\> Dies kann im `init` geschehen
	- Vorsicht, wenn man hier Constraints in der aktuellen Hierarchie bearbeitet. =\> Dadurch wird ein Update-Step aufgerufen und anschliessend wieder ein Layout-Step (es braucht also eine Abbruch-Bedingung)

##  Manuell aufrufen
- `layoutSubviews()` sollte man nicht manuell aufrufen.
- Das Layout wird automatisch invalidiert wenn man constraints hinzufügt oder entfernt oder views zur Hierarchie hinzufügt oder entfernt
- Beim nächsten Layout Pass wird es dan neu berechnet
- Wenn man es aber trotzdem manuell auslösen muss:
	- Zuerst `setNeedsLayout()` zum invalidieren und anschliessend `layoutIfNeeded()` aufgerufen.
	- Meistens möchte man dass, wenn man sofort ein Resultat benötigt, z.B. weil man sofort das neue Frame der View kennen muss
##  Zusammenfassung
- Wann ruft das System die Methode auf?
- Wozu kann man es nutzen?


#learning unit#