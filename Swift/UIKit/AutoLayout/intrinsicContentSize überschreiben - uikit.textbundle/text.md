# intrinsicContentSize überschreiben - UIKit
↔️

##  Beispiel

Hier macht man einen Button, der wie von Apple empfohlen 44 Punkte gross sein soll (der UIButton hat nur 30 Punkte!)

```swift
class BaseButton: UIButton {
    override var intrinsicContentSize: CGSize {
        let superSize = super.intrinsicContentSize
        return CGSize(width: superSize.width, height: 44)
    }
}
```

## Tipp: Wenn man nur eine Dimension hat

- Wenn man nur eine intrinsicContentSize für eine Dimension hat, dann kann man für die andere Dimension `UIView.noIntrinsicMetric` zurückgeben.

##  Intrinsic Content Size

Die Intrinsic Content Size bezieht sich jeweils auf das Alignment Frame

## Dynamische Intrinsic Content Size

- In diesem Fall kann man mit `invalidateIntrinsicContentSize()` das System informieren, dass sich die Intrinsic Content Size verändert hat.

##  Zusammenfassung
- Code
- Was tut man, wenn man nur eine Dimension hat?

#learning unit#