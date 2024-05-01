# @MainActor Annotation
🤴

##  Wo kann man @MainActor verwenden?

- Man kann sowohl ganze Klassen als auch einzelne Properties oder Funktionen mit `@MainActor` kennzeichnen

```swift
class Test {
    var x: Int = 5

    @MainActor
    func changeX() {
        x = 10
    }
}
```

```swift
@MainActor
class Test {
    var x: Int = 5

    func changeX() {
        x = 10
    }
}
```

```swift
class Test {
    @MainActor
    var x: Int = 5
}
```

## Was ist die Auswirkung?

- Wenn man Klassen und Methoden mit @MainActor kennzeichnet, werden die Methoden dadurch implizit `async` wenn sie aus einem background thread verwendet werden (weil es könnte ja sein, dass man auf den MainActor warten muss...)

```swift
Task.detached {
	await test.changeX()
}
```

- Wenn man sich sowieso in einem Synchronen Kontext befindet, braucht es das await nicht:

```swift
await MainActor.run {
    test.changeX()
}
```


Wenn man ein Property als @MainActor kennzeichnet, dann kann man es nur in einem synchronen Kontext verändern (weil man kein await machen kann)

```swift
Task.detached {
    await MainActor.run {
        test.x = 10
    }
}
```

ansonsten hätte man eine Fehlermeldung
![][image-1]

##  Zusammenfassung
- Was ist die Auswirkung wenn man @MainActor auf einer Klasse, einer Methode oder einem Property verwendet?

[image-1]:	assets/Bildschirmfoto%202024-04-10%20um%2009.03.12.png

#learning unit#