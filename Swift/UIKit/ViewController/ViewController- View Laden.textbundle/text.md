# ViewController: View Laden
🏁

## Codebeispiel

```swift
class ViewController: UITableViewController {
    
    var pictures: [String] = []

	//loadView() gets called before viewDidLoad()
	//braucht man nicht, wenn es vom Storyboard geladen wird
	override func loadView() {
		//...
		//Hier könnte man die eigentliche view noch zuweisen
		//view = ...
	}

    override func viewDidLoad() {
        super.viewDidLoad()
        
       	//load data
		pictures = ...
    }

}
```


## Zusammenfassung
- Beispiel: Ein View-Controller mit zwei override-Funktionen: Einmal um eine View zu setzen und einmal um die View zu konfigurieren

#learning unit#