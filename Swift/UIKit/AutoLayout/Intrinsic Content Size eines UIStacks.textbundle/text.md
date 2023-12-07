# Intrinsic Content Size eines UIStacks
🥞

## Verhalten
- Standartmässig verwendet ein Stack immer die minimal nötige Grösse, in der alle Constraints erfüllt werden

![][image-1]

## Minimal Example

```swift
import UIKit

class ViewController: UIViewController {
    override func viewDidLoad() {
        super.viewDidLoad()

        //Stack
        let stack = UIStackView()
        stack.axis = .vertical
        view.addSubview(stack)

        //Labels
        let label = UILabel()
        label.text = "Hello World"

        let label2 = UILabel()
        label2.text = "Hello World 2"

        stack.addArrangedSubview(label)
        stack.addArrangedSubview(label2)

        //Constraints
        stack.translatesAutoresizingMaskIntoConstraints = false

        NSLayoutConstraint.activate([
            stack.topAnchor.constraint(equalTo: view.safeAreaLayoutGuide.topAnchor),
            stack.leadingAnchor.constraint(equalTo: view.safeAreaLayoutGuide.leadingAnchor)
        ])

        //Background
        stack.backgroundColor = .red
    }
}
```

## Zusammenfassung
- Wie ist die Intrinsic Content Size eines UIStacks?

[image-1]:	assets/simulator_screenshot_1956092B-D63C-405E-9386-3CC593F342A2.png

#learning unit#