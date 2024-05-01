# Dispatch Group
🎛️

##  Zweck
- Mit einer Dispatch Group kann man ein Callback ausführen sobald mehrere andere Callbacks abgeschlossen sind:

![][image-1]

[https://developer.apple.com/documentation/dispatch/dispatchgroup][1]

## Beispiel: Code ausführen wenn andere Callbacks abgeschlossen sind

```swift
let dispatchGroup = DispatchGroup()

dispatchGroup.notify(queue: .main) { 
    //beide callbacks sind abgeschlossen
}

dispatchGroup.enter()
doSomething(onCompletion: {
    dispatchGroup.leave()
})

dispatchGroup.enter()
doSomethingElse(onCompletion: {
    dispatchGroup.leave()
})
```

##  Beispiel: Auf die Gruppe warten

Man kann auch synchron auf die Gruppe warten:

```swift
group.wait()
```

## Zusammenfassung
- Konzept, nicht den genauen Code

[1]:	https://developer.apple.com/documentation/dispatch/dispatchgroup

[image-1]:	assets/DraggedImage.png

#learning unit#