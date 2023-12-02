# NavigationController
🧭

## Programmatisch 

```swift
let favoritesListVC = FavoritesListVC()
favoritesListVC.title = "Favorites"

return UINavigationController(rootViewController: favoritesListVC)
```

## Im Storyboard

### Bestehende View in Navigation Controller embedden

Achtung: Man muss die View embedden, nicht den View Controller!
 
![][image-1]

oder:

![][image-2]

### Neue View Pushen

Siehe Kapitel: „UINavigationController neuen ViewController pushen ohne Segue“

###  Navigation Controller konfigurieren

Beachte: Man macht in in diesem Beispiel kein eigenes Swift File für den Navigation Controller. Stattdessen kann man den Navigation Controller in derjenigen View anpassen, die im View Controller liegt:

```swift
self.navigationController?
```

### HideNavigationBar on Tab

Achtung: weil das die Touches empfängt soll man es nur in der Detailansicht machen

```swift
override func viewWillAppear(_ animated: Bool) {
    super.viewWillAppear(animated)
    navigationController?.hidesBarsOnTap = true
}

override func viewWillDisappear(_ animated: Bool) {
    super.viewWillDisappear(animated)
    navigationController?.hidesBarsOnTap = false
}
```

## Titel festlegen

Das kann man auch für die Untertitel machen. Beachte: Der Titel wird in der Subview festgelegt, die im NavigationController liegt:

```swift
//Diese view ist in den navigation controller eingebettet
class ViewController: UITableViewController {
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
        
        title = "Storm Viewer"
        navigationController?.navigationBar.prefersLargeTitles = true
    }
}
```

=\> Sollte man in der Regel nur in der ersten Ansicht festlegen.

Aber: alle Unterviews erben diese eigenschaft, desshalb sollte man es bei den Unterviews wieder herausnehmen:

```swift
//das ist die Detail-View, die angezeigt wird, wenn etwas in der Table view angeklickt wird
override func viewDidLoad() {
	navigationItem.title = "mySubtitle"
	navigationItem.largeTitleDisplayMode = .never
}
```

Beachte: Dieses mal heisst es `navigationItem`, weil es nur um diesen einen Screen geht.

> Each view controller has its own navigationItem

Man kann sogar eine View als Titel hinzufügen:

```swift
navigationItem.titleView = listStyleSegmentedControl
```

##  Einen Button hinzufügen / UIToolbar

### Eigener Button einfügen

Innerhalb von `viewDidLoad`:

```swift
navigationItem.rightBarButtonItem = UIBarButtonItem(barButtonSystemItem: .action, target: self, action: #selector(shareTapped))
```

The .action system item displays an arrow coming out of a box, signaling the user can do something when it's tapped.
![][image-3]

Man kann auch einen eigenen Titel verwenden:

```swift
navigationItem.rightBarButtonItem = UIBarButtonItem(title: "Open", style: .plain, target: self, action: #selector(openTapped))

```

Beachte: Die aufgerufene Funktion brauch `@objc`

```swift
@objc func shareTapped() {
	//...    
}
```

@IBAction automatically implies @objc: Because @IBAction means you're connecting storyboards (Objective-C code) to Swift code, it always implies @objc as well.

### Edit Buttons

```swift
navigationItem.rightBarButtonItem = editButtonItem
```

![][image-4]

Anschliessend folgendes überschreiben:

```swift
override func setEditing(_ editing: Bool, animated: Bool) {
	//...
}
```


### Refresh Buton

```swift
let refresh = UIBarButtonItem(barButtonSystemItem: .refresh, target: webView, action: #selector(webView.reload))
```

### Spacer

```swift
let spacer = UIBarButtonItem(barButtonSystemItem: .flexibleSpace, target: nil, action: nil)
```


### Buttons über das Storyboard bearbeiten

Man kann auch im Storyboard einfach die BarButtonItems reinziehen. Bei System Item kann man zum Beispiel auch schon direkt „Add“ auswählen:

![][image-5]

### Mehrere Buttons zuweisen


```swift
navigationItem.rightBarButtonItems = [downButton, upButton]
```

### Toolbar anzeigen

```swift
toolbarItems = [spacer, refresh]
navigationController?.isToolbarHidden = false
```

![][image-6]

## Zusammenfassung
- Wie erstellt man programmatisch einen navigation Controller, welche einen ViewController mit Titel enthält?

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-03-16%20um%2014.47.00.png
[image-2]:	assets/Bildschirmfoto%202021-09-03%20um%2015.33.41.png
[image-3]:	assets/Bildschirm%C2%ADfoto%202023-03-17%20um%2008.02.06.png
[image-4]:	assets/Bildschirmfoto%202021-09-03%20um%2015.52.33.png
[image-5]:	assets/Bildschirmfoto%202021-09-03%20um%2015.53.53.png
[image-6]:	assets/Bildschirm%C2%ADfoto%202023-03-19%20um%2014.24.07.png

#learning unit#