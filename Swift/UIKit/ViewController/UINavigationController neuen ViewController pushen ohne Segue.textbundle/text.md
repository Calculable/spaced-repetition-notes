# UINavigationController neuen ViewController pushen ohne Segue
🥞

```swift
//Normalerweise hat man schon direkt zugriff auf das Storyboard, aber zum Beispiel im AppDelegate muss man zuerst eine Referenz auf das Storyboard erhalten:
let storyboard = UIStoryboard(name: "Main", bundle: nil)
//allenfalls kann man auch einfach storyboard? schreiben
let vc = storyboard.instantiateViewController(identifier: "SecondVC") as! MyViewController
//change the view controller
    vc.selectedImage = pictures[indexPath.row]
self.navigationController?.pushViewController(vc, animated: true)
```

Beachte: Damit das funktioniert, braucht der ViewController einen Identifier:

![][image-1]


## Zusammenfassung
Wie kann man einen neue View auf den Stack pushen (ohne Segue)

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-01-11%20um%2020.06.19.png

#learning unit#