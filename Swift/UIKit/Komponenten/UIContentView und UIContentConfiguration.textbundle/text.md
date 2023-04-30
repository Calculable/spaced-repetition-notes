# UIContentView und UIContentConfiguration
🌅

## Übersicht

![][image-1]

## Um was geht es?
- Eine Content View kümmert sich um die Darstellung des Inhalts, die Konfiguration um das Model und den State
- Bei jeder Änderung wird die Konfiguration neu angewendet, so bleiben Model und View immer synchronisiert
- Reusability wird besser, weil man die View an verschiedenen Orten mit unterschiedlichen Konfigurationen einsetzen kann.

##  Configuration

###  Zweck
- Beschreibt Content und Styling
- Enthält das Model

### Benötigte Funktionen
- `makeContentView()`: Erstellt eine Content View mit sich selbst als Konfiguration.
- Aktualisiert sich selbst für einen bestimmten Status (z.B. `selected` oder `highlighted`)

###  Codebeispiel
```swift
struct ReminderContentConfiguration: UIContentConfiguration {
    var reminder: Reminder //Our Model
    
    func makeContentView() -> UIView & UIContentView {
        return ReminderContentView(self)
    }

    func updated(for state: UIConfigurationState) -> ReminderContentConfiguration {
        return self
    }

    mutating func updateReminderPriority(to newPriority: Int) {
        reminder.currentReminderPriority = newPriority
    }
}
```

- Beachte: Die Content View bietet auch die Funktionen an, um das Model zu aktualisieren
- Hinweis: Die View soll das Model nicht direkt aktualisieren, da man ja eine Trennung zwischen View und Model haben möchte

## Codebeispiel

- Beachte: Es gibt keine Referenz auf das Model

```swift
class ReminderContentView : UIView, UIContentView {
    
    let prioritySlider = UISlider()

	var configuration: UIContentConfiguration {
	    didSet {
	        self.configure(configuration: configuration)
	    }
	}
    
    init(_ configuration: UIContentConfiguration) {
        self.configuration = configuration
		super.init(frame: .zero)
        self.addSubview(prioritySlider)
		//configure slider....
        prioritySlider.addTarget(self, action: #selector(self.sliderValueDidChange(_:)), for: .valueChanged)
        

    }

	func configure(configuration: UIContentConfiguration) {
	    guard let configuration = configuration as? ReminderContentConfiguration else { return }
	    self.prioritySlider.value = Float(configuration.reminder.currentReminderPriority) //hier wird auf das Model zugegriffen
	}

	@objc func sliderValueDidChange(_ sender: UISlider!) {
	    // Snap the slider value to integer steps.
	    guard var configuration = configuration as? ReminderContentConfiguration else { return }
	    configuration.updateReminderPriority(to: sender.value)
	    self.configure(configuration: configuration)
	}
}
```



## Häufiger Anwendungsfall von ContentViews: Cell’s

```swift
var contentConfiguration = cell.defaultContentConfiguration()
contentConfiguration.text = text(for: row)
contentConfiguration.textProperties.font = UIFont.preferredFont(forTextStyle: row.textStyle)
contentConfiguration.image = row.image
cell.contentConfiguration = contentConfiguration
```


##  Zusammenfassung
- Zweck
- Nicht genauer Code

[image-1]:	assets/DraggedImage.png

#learning unit#