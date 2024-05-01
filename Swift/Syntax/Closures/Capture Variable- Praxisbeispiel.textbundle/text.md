# Capture Variable: Praxisbeispiel
🦋

##  Codebeispiel

```swift
class ExampleViewController: UIViewController {

    var a: A? = nil

    override func viewDidLoad() {
        super.viewDidLoad()
        callbackExample()
    }

    private func callbackExample() {
        var counter = 0

        a = A(callback: {
            counter+=1
            print("The counter is \(counter)")
        }) //callback wird jede Sekunde einmal aufgerufen

    }
}
```


## Fragen

- Was gibt der Counter aus?
- Wäre das ein Retain-Cycle?


##  Antworten

Das Programm zählt den Counter hoch:

```swift
The counter is 1
The counter is 2
The counter is 3
...
```

Es wird also eine Referenz zum `counter` "gecaptured" (obwohl der counter ein primitiver value-type ist!)

Weil counter eine lokale Variable ist entsteht auch kein Retain-Cycle:

![][image-1]

Anders würde es hier aussehen, wenn `counter` eine Instanzvariable wäre. Das hier wäre ein Retain-Cycle:

```swift
class ExampleViewController: UIViewController {

    var a: A? = nil
    var counter = 0

    override func viewDidLoad() {
        super.viewDidLoad()
        callbackExample()

    }

    private func callbackExample() {

        a = A(callback: {
            self.counter+=1 //strong capture of self
            print("The counter is \(self.counter)")
        })

    }
}
```

![][image-2]

(Hier müsste man `[weak self]` verwenden)

Wenn man statt "Capture Variable" stattdessen "Capture Value" verwendet, hat man eine unveränderbare Kopie von `counter`:


```swift
class ExampleViewController: UIViewController {

    var a: A? = nil

    override func viewDidLoad() {
        super.viewDidLoad()
        callbackExample()

    }

    private func callbackExample() {
        var counter = 0

        a = A { [counter] in
            //counter ist nicht veränderbar, immutable capture
            print("The counter is \(counter)")
        }

    }
}
```

## Theorie
Siehe [ulysses://x-callback-url/open?id=bgFnRdBdxpLTG\_9iIaWGRQ][1]

##  Zusammenfassung
- Codebeispiel anschauen, Fragen beantworten

[1]:	ulysses://x-callback-url/open?id=bgFnRdBdxpLTG_9iIaWGRQ

[image-1]:	assets/Bildschirmfoto%202024-03-06%20um%2013.32.24.png
[image-2]:	assets/Bildschirmfoto%202024-03-06%20um%2013.27.55.png

#learning unit#