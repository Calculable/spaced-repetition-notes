# Methode layoutSubviews()
🧩

## Zweck

- Hier aktualisiert man die Views mit den Frames, welche zuvor mit `updateConstraints` berechnet wurden. (`updateConstraints` selbst muss man nur selten überschreiben...)
- Dies geschieht **Top-Down ** (zuerst Superview und dann subview)
- Hier kann man Konfigurationen definieren, welche von der Grösse der View abhängen.

## Beispiel

- Man möchte zum Beispiel einen Corner-Radius von der View-Grösse abhängig machen:

```swift
override func layoutSubviews() {
    super.layoutSubviews()
    containerView.layer.masksToBounds = true
    containerView.layer.cornerRadius = 0.5 * containerView.bounds.width
}
```


##  Überschreiben

- Wird häufig überschrieben ::!::
- z.B. Wenn Constraints alleine nicht ausreichen für das Layout
- `super.layoutSubviews()` nicht vergessen!

## Was sollte man hier nicht aufrufen?

- Hier sollte man keine Constraints der View ausserhalb der aktuellen Hierarchie bearbeiten.
	- Dies ist nicht der Ort, wo man generell Constraints definieren sollte. =\> Dies kann im `init` geschehen
	- Vorsicht, wenn man hier Constraints in der aktuellen Hierarchie bearbeitet. =\> Dadurch wird ein Update-Step aufgerufen und anschliessend wieder ein Layout-Step (es braucht also eine Abbruch-Bedingung)

## Wann wird es aufgerufen?
- nach `updateConstraints`
- Die Methode wird auch aufgerufen, wenn sich die View-Grösse verändert


##  Wie wird es aufgerufen?

- Wird durch `setNeedsLayout` und anschliessend mit `layoutIfNeeded` aufgerufen.

## Für View Controller

- Das ist für Views
- Für UIController gibt es hingegen `viewWillLayoutSubviews` und `viewDidLayoutSubviews`

##  Zusammenfassung
- Zweck dieser Methode?
- Wann ruft das System die Methode auf?


#learning unit#