# Observable Makro für SwiftUI - State
👀

## Import

```swift
import Observation
```

##  Vorher

```swift
public class FoodTruckModel: ObservableObject {
	@Published public var truck = Truck ()
}
```

##  Nachher

```swift
@Observable class FoodTruckModel {    
  var donuts = truck = Truck ()
}
```


##  Keine Annotation: Lesender Zugriff

Zum Beispiel für Structs oder Klassen die von der Parent View verändert werden

```swift
let donutToAdd: Donut
```

Früher: `@StateObject/@ObservedObject`

> If a view owns a property or gets it from a parent but doesn’t need to change it, use let.

Achtung: In der Praxis funktioniert of auch der Schreibende Zugriff, das sollte man aber nicht verwenden!


## @State: Schreibender Zugriff

Wenn es Teil der View ist:

```swift
@State private var donutToAdd: Donut = Donut()
```

Funktioniert für Structs und Klassen

Früher: `@StateObject/@ObservedObject`

## Property Ignorieren

> In case anyone else runs across this… Using @Observable on a class that has a property that is a closure causes the Xcode beta 3 compiler to flip out. Using @ObservationIgnored on the said property will get the compiler to calm down.


## Welche Properties werden beobachtet?

- Diejenigen die im view body verwendet werden
- Funktioniert auch mit Computed Property

## Zusammenhang mit @Model (Swift Data)

- Eine Klasse mit @Model hat gleichzeitig auch alle Eigenschaften von @Observable

##  Zusammenfassung
- Wie sieht ein Model aus: Vorher / Nachher
- Wann braucht man @State?

#learning unit#