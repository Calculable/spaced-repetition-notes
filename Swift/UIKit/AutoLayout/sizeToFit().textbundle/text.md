# sizeToFit()
↔️

- Das wird auf einer View aufgerufen
- Damit benötigt die View genau den minimalen Platz, den es für seinen Inhalt braucht
- Das ist vor allem dann sinnvoll, wenn man nicht weiss, wie gross das Element sein soll weil es zum Beispiel Text enthält
- Tipp: Nicht verwechseln mit dem `.fixedSize()` Modifier von SwiftUI


## Beispiel

```swift
class ViewController: UIViewController {
    override func viewDidLoad() {
        super.viewDidLoad()
        
        let commentLabel = UILabel()
        commentLabel.numberOfLines = 0 // Allows label to use as many lines as needed
        commentLabel.text = "This is a dynamically sized label. It can expand to fit a large amount of text without truncating. sizeToFit() will be used to make sure all the content is visible."
        
        // Layout the label with constraints to define its x, y, and width (optional)
        commentLabel.translatesAutoresizingMaskIntoConstraints = false
        view.addSubview(commentLabel)
        
        NSLayoutConstraint.activate([
            commentLabel.topAnchor.constraint(equalTo: view.topAnchor, constant: 20),
            commentLabel.leadingAnchor.constraint(equalTo: view.leadingAnchor, constant: 20),
            commentLabel.trailingAnchor.constraint(equalTo: view.trailingAnchor, constant: -20)
            // Note: No need to set the height constraint
        ])
        
        // Call sizeToFit() to adjust the height of the label after setting its text
        commentLabel.sizeToFit()
    }
}
```

=\> Hier weiss man nicht im Vorfeld, wie gross das Label sein soll. Mit `sizeToFit` wird die Höhe dann automatisch gesetzt. 

- Man muss es auch nicht bei jeder Screenänderung mehr aufrufen (zum Beispiel wenn der Screen rotiert wird)

##  Zusammenfassung
- Was macht die Funktion?

#learning unit#