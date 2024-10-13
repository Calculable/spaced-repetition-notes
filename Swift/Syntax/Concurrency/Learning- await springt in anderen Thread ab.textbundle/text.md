# Learning: await springt in anderen Thread ab
🦘

##  Beispiel
- System springt bei `await`-XY in einen anderen Thread:

```swift
struct ContentView: View {
    var body: some View {
        Button("Do Something") {
            Task {
                print("isMainThread: \(Thread.isMainThread)")
                await doSomething()
                print("isMainThread: \(Thread.isMainThread)")
            }
        }
    }

    func doSomething() async {
        print("isMainThread: \(Thread.isMainThread)")
    }
}
```


## Ausgabe

```swift
isMainThread: true
isMainThread: false
isMainThread: true
```

Beachte: Am Verhalten ändert sich auch mit dem nichts:

```swift
Task { @MainActor in

}
```

## Auswirkung
- Aus diesem Grund muss man in den meisten Fällen nicht `Task.detached{}` verwenden.

#learning unit# #guide