# Array of observable objects
🧠

Beachte: Hier wird die „changed“ Notifikation nicht ausgelöst:

```swift
var greeting = "Hello, playground"

class StringBox: ObservableObject {
    @Published var myString: String
    
    init(_ myString: String) {
        self.myString = myString
    }
}

class StringBoxArray: ObservableObject {
    @Published var boxes: [StringBox]
    
    init() {
        boxes = [StringBox("1"), StringBox("1"), StringBox("1")]
    }
    
}

var boxArray = StringBoxArray()
boxArray.objectWillChange.sink(receiveValue: {
    print("changed")
})

boxArray.boxes[0].objectWillChange.send()

print("Hello")
```

Fazit: Ein Observable object mit einem Array von anderen observable Objects wird nicht informiert, selbst wenn ein Objekt innerhalb des Array `objectWillChange` aufruft.

## Damit es funktioniert, muss man einen rechten Aufwand betreiben (nicht können)

```swift
import Foundation
import SwiftUI
import Combine

var greeting = "Hello, playground"

class ObservableArray<T>: ObservableObject {

    @Published var array:[T] = []
    var cancellables = [AnyCancellable]()

    init(array: [T]) {
        self.array = array

    }

    func observeChildrenChanges<T: ObservableObject>() -> ObservableArray<T> {
        let array2 = array as! [T]
        array2.forEach({
            let c = $0.objectWillChange.sink(receiveValue: { _ in
                self.objectWillChange.send()
                print("changed2")
            })

            // Important: You have to keep the returned value allocated,
            // otherwise the sink subscription gets cancelled
            self.cancellables.append(c)
        })
        return self as! ObservableArray<T>
    }


}


class StringBox: ObservableObject {
    @Published var myString: String
    
    init(_ myString: String) {
        self.myString = myString
    }
}

class StringBoxArray: ObservableObject {
    @Published var boxes: ObservableArray<StringBox>
    var cancellables = [AnyCancellable]()
    
    init() {
        boxes = ObservableArray(array: [StringBox("1"), StringBox("1"), StringBox("1")]).observeChildrenChanges()
        let c = boxes.objectWillChange.sink(receiveValue: {
            print("changed3")
            self.objectWillChange.send()
        })
        self.cancellables.append(c)
    }
    
}

var boxArray = StringBoxArray()
boxArray.objectWillChange.sink(receiveValue: {
    print("changed")
})

boxArray.boxes.array[0].objectWillChange.send()

print("Hello4")

```

## Zusammenfassung
- Was ist das Problem wenn man in einem `ObservableObject` ein `@Published` array hat, dessen Elemente ebenfalls `ObservableObject`s sind?
- (Nur Problem kennen, nicht die Lösung)

#nur learning unit# #learning unit#