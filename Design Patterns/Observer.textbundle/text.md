
# Observer
🥸

## Zweck

- Verbreitet in Swift
- Vor allem für Views

##  Beispiel

```swift
import XCTest

class Subject {
    var state: Int = 5

     private lazy var observers = [Observer]()

    func attach(_ observer: Observer) {
        observers.append(observer)
    }

    func notify() {
        observers.forEach({ $0.update(subject: self)})
    }

     func someBusinessLogic() {
        state = 4
        notify()
    }
}

protocol Observer: class {
    func update(subject: Subject)
}


class ConcreteObserverA: Observer {
    func update(subject: Subject) {
        if subject.state < 3 {
            print("ConcreteObserverA: Reacted to the event.\n")
        }
    }
}

/// Let's see how it all works together.
class ObserverConceptual: XCTestCase {
    func testObserverConceptual() {
        let subject = Subject()
        let observer1 = ConcreteObserverA()
        subject.attach(observer1)
        subject.someBusinessLogic()
    }
}
```

## Zusammenfassung
- Beispiel-Implementation

#nur learning unit# #learning unit#