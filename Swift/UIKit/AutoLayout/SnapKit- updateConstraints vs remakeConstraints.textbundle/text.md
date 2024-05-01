# SnapKit: updateConstraints vs remakeConstraints
🫰

##  Remake Constraints
- Bei remakeConstraints werden ALLE vorherigen Constraints von der View entfernt und nur noch die neuen Constraints angewendet

##  Update Constraints

- Bei updateConstraints bleiben die bisherigen constraints bestehen, aber man kann einzelne Constraints (zum Beispiel `make.center` aktualisieren)
- ACHTUNG: Wenn man einen Constraint "updaten" will der zuvor nicht existiert hat, dann crasht die App
- Oftmals verwendet man das für Animationen

```swift
self.growingButton.snp.updateConstraints { (make) -> Void in
        make.center.equalTo(self);
        make.width.equalTo(self.buttonSize.width).priority(250)
        make.height.equalTo(self.buttonSize.height).priority(250)
        make.width.lessThanOrEqualTo(self)
        make.height.lessThanOrEqualTo(self)
    }
}
```


##  Zusammenfassung
- Was ist der Unterschied zwischen diesen beiden?

#learning unit#