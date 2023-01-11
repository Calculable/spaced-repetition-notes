# UINavigationController neuen ViewController pushen ohne Segue 🥞

```swift
let storyboard = UIStoryboard(name: "Main", bundle: nil)
//allenfalls kann man auch einfach storyboard? schreiben
let vc = storyboard.instantiateViewController(identifier: "SecondVC")
self.navigationController?.pushViewController(vc, animated: true)
```

## Zusammenfassung
Wie kann man einen neue View auf den Stack pushen (ohne Segue)
