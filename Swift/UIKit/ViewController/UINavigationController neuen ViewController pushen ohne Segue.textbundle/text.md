# UINavigationController neuen ViewController pushen ohne Segue
🥞

```swift
let storyboard = UIStoryboard(name: "Main", bundle: nil)
//allenfalls kann man auch einfach storyboard? schreiben
let vc = storyboard.instantiateViewController(identifier: "SecondVC")
self.navigationController?.pushViewController(vc, animated: true)
```

Beachte: Damit das funktioniert, braucht der ViewController einen Identifier:

![][image-1]


## Zusammenfassung
Wie kann man einen neue View auf den Stack pushen (ohne Segue)

[image-1]:	assets/Bildschirm%C2%ADfoto%202023-01-11%20um%2020.06.19.png

#nur learning unit#