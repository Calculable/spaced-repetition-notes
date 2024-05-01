# Custom Layout mit expliziten Frames
🖼️
- Nur für den Ausnahmefall, ansonsten ist Constraint-basiertes Layout empfohlen

```swift
public class MyView: UIView {
	override public func layoutSubviews() {
        super.layoutSubviews()

		//Hier ist die eigene grösse bekannt: self.frame.width, self.frame.height

		//Mit dieser Info kann man nun die Subviews layouten:

		subview.frame = ...
    }
}
```

##  Zusammenfassung
- In welcher Lifecycle-Methode kann man Subviews "von Hand" platzieren?

#learning unit#