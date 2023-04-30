# Constraints animieren
🎦

```swift
class ProgressHeaderView: UICollectionReusableView {
    var progress: CGFloat = 0 {
        didSet {
			setNeedsLayout()
            heightConstraint?.constant = progress * bounds.height
            UIView.animate(withDuration: 0.2) { [weak self] in
                self?.layoutIfNeeded()
            }
        }
    }

	//...
}
```

> The layoutIfNeeded() method forces the view to update its layout immediately 

## Zusammenfassung
Code

#learning unit#