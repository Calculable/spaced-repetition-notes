# Beispiel Combine Begriffe
🔀

##  Code
```swift
import UIKit
import Combine

class ViewController: UIViewController {
    @Published var read = false
    @Published var practiced = false
    @Published var approved = false

    private var cancellables: Set<AnyCancellable> = []

    override func viewDidLoad() {
        super.viewDidLoad()
        setupPlayButton()
    }

    private func setupPlayButton() {
        Publishers.CombineLatest3($read, $practiced, $approved)
            .map { $0 && $1 && $2 }
            .assign(to: \.isEnabled, on: playButton)
            .store(in: &cancellables)
    }

	//...
}
```

##  Lösung
- `$read`, `$practiced`, `$approved` sind Publisher
- `Publishers.CombineLatest3($read, $practiced, $approved)` gibt einen Publisher zurück
- `map` ist eine Hilfsfunktion, welche einen Operator erstellt (und einen Publisher zurückgibt)
- `assign` ist eine Hilfsfunktion, welche einen Subscriber erstellt (und eine Subscription zurückgibt)

##  Zusammenfassung
- Siehe Codebeispiel
- Was sind $read, $practiced, $approved 
- Was macht .map, was gibt es zurück?
- was macht .assign, was gibt es zurück?

#learning unit# #guide