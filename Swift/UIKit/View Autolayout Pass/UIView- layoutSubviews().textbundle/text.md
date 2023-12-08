# UIView: layoutSubviews()
🧩

## Zweck

- Wird aufgerufen, wenn die Child-Views neu positioniert werden müssen (idr. weil sich das Frame verändert hat oder weil child-views hinzugefügt oder entfernt wurden)
- Dies geschieht **Top-Down ** (zuerst Superview und dann subview)
- Hier kann man Konfigurationen definieren, welche von der Grösse der View abhängen.
- Für UIController gibt es hingegen `viewWillLayoutSubviews` und `viewDidLayoutSubviews`


## Beispiel

- Man möchte zum Beispiel einen Corner-Radius von der View-Grösse abhängig machen:

```swift
override func layoutSubviews() {
    super.layoutSubviews()
    containerView.layer.masksToBounds = true
    containerView.layer.cornerRadius = 0.5 * containerView.bounds.width
}
```

- Wird häufig überschrieben
- z.B. Wenn Constraints alleine nicht ausreichen für das Layout
- `super.layoutSubviews()` nicht vergessen!

## Was sollte man hier nicht aufrufen?

- Hier sollte man keine Constraints der View ausserhalb der aktuellen Hierarchie bearbeiten.
	- Dies ist nicht der Ort, wo man generell Constraints definieren sollte. =\> Dies kann im `init` geschehen
	- Vorsicht, wenn man hier Constraints in der aktuellen Hierarchie bearbeitet. =\> Dadurch wird ein Update-Step aufgerufen und anschliessend wieder ein Layout-Step (es braucht also eine Abbruch-Bedingung)

##  Manuell aufrufen

- Wird durch `setNeedsLayout()` und anschliessend mit `layoutIfNeeded()` aufgerufen.

##  Zusammenfassung
- Wann ruft das System die Methode auf?
- Wozu kann man es nutzen?


#learning unit#