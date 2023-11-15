# Observable Makro
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


## Property Ignorieren

> In case anyone else runs across this… Using @Observable on a class that has a property that is a closure causes the Xcode beta 3 compiler to flip out. Using @ObservationIgnored on the said property will get the compiler to calm down.


## Welche Properties werden beobachtet?

- Diejenigen die im view body verwendet werden
- Funktioniert auch mit Computed Property

## Zusammenhang mit @Model (Swift Data)
- Eine Klasse mit @Model hat gleichzeitig auch alle Eigenschaften von @Observable

##  Zusammenfassung
- Wie sieht ein Model aus: Vorher / Nachher


#learning unit#