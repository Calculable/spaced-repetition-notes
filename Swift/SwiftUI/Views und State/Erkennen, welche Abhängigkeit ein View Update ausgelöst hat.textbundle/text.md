# Erkennen, welche Abhängigkeit ein View Update ausgelöst hat
🔄

Mit `Self.printChanges()` 

Hinweis: Dieser Aufruf sollte man entfernen, wenn man die App in den Store einreicht.

```swift
struct ContentView: View {
    @StateObject private var myChangingObject = MyChangingObject()

    var body: some View {
        let _ = Self._printChanges()
        Text("Hello World")
    }
}
```


![][image-1]

##  Zusammenfassung
- Wie findet man heraus, welche Abhängigkeit ein View-Update ausgelöst hat

[image-1]:	assets/2023-07-12%2016.01.39.gif

#learning unit#