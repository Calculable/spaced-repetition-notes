# SwiftUI Bug: abgeschnittener Text
✂️

## Problem
Manchmal sind Texte im VStack abgeschnitten, auch wenn im VStack theoretisch genügend Platz ist

```swift
struct ContentView: View {
    var body: some View {
        VStack {
            Text(firstText)
            Text(secondText)
        }
    }
}
```
![][image-1]


## Ursache
- Vermutlich ein SwiftUI Bug?

## Lösung

`minimumScaleFactor` Hinzufügen

```swift
struct ContentView: View {
    var body: some View {
        VStack {
            Text(firstText)
				.minimumScaleFactor(0.5) 
            Text(secondText)
        }
    }
}
```
![][image-2]

##  Zusammenfassung
- Problem
- Lösung


[image-1]:	assets/Bildschirmfoto%202023-08-02%20um%2015.59.50.png
[image-2]:	assets/Bildschirmfoto%202023-08-02%20um%2016.00.39.png

#learning unit#