# View programmatisch hinzufügen

Mit `view.addSubview(label)`

Beispiel:

```swift
override func viewDidLoad() {
    super.viewDidLoad()
    var label = UILabel()
    label.text = "Hello World"
    label.translatesAutoresizingMaskIntoConstraints = false
    view.addSubview(label)
    label.centerXAnchor.constraint(equalTo: view.centerXAnchor).isActive = true
    label.centerYAnchor.constraint(equalTo: view.centerYAnchor).isActive = true
}
```

## Zusammenfassung
- Benötigter Befehl

#learning unit#