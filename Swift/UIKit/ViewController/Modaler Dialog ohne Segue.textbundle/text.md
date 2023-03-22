# Modaler Dialog ohne Segue
🗒️

## Code

Hier muss man den anzuzeigenden ViewController zuerst instanzieren:

```swift
let storyboard = UIStoryboard(name: "Main", bundle: nil)
//allenfalls kann man auch einfach storyboard? schreiben

let selectionVC = storyboard.instantiateViewController(identifier: "SelectionScreen") as! SelectionViewController
//allenfalls: selectionVS.delegate = self
present(selectionVC, animated: true, completion: nil)
```

So kann der Modale Dialog wieder geschlossen werden:

```swift
dismiss(animated:  true, completion:  nil)
```

Hier wird die Storyboard ID festgelegt:

![][image-1]

## Wichtig! Siehe auch:

Siehe auch „UIKit: Optionale Properties vermeiden mit Dependency Injection“

## Zusammenfassung
- Wie kann man einen modalen Dialog ohne Segue anzeigen?
- Wie wird der modale Dialog wieder geschlossen?

[image-1]:	assets/Bildschirmfoto%202021-09-01%20um%2011.58.15.png

#learning unit#