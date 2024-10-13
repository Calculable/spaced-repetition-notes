# Combine: Grundlagen
🔀

## Zweck

- Combine ist eine Swift API, um Werte in einer asynchronen Pipeline zu transformieren und weiterzugeben.

## Import

```swift
import Combine
```

## Übersicht

![][image-1]

## Publisher ⬆️

### Zweck
- Veröffentlicht Werte
- Man kann nicht Manuell Werte einfügen (es ist also eine Source of Truth)

### Einzelner Wert sofort publishen, anschliessend terminieren
```swift
let publisher1 = Just(42)
```

### Mehrere Werte sofort publishen, anschliessend terminieren
```swift
let publisher2 = [1,2,3,4,5].publisher
```

### "Publisher für einen einzelnen Wert"
- Das nennt man ein "Future" - ein Wert der erst in Zukunft verfügbar wird

## Subject ↕️

### Zweck
- Spezieller Typ eines Publishers, bei dem man auch manuell Werte senden kann
- Ein Subject ist gleichzeitig auch ein Subscriber weil es Werte von andern Publishern empfangen und weiterleiten kann.

### PassthroughSubject

Hinweis: Zum Zeitpunkt wo man `send` aufruft muss man schon subscribed sein, ansonsten gehen die Werte verloren!

```
let mySubject = PassthroughSubject<String, Never>()
mySubject.send("Hello")
mySubject.send("World!")
```

![][image-2]

### CurrentValueSubject

Hier wird NUR der letzte Wert aufbewahrt, die anderen gehen verloren. Dafür bekommt man nach dem `sink` direkt einen Wert (beachte: am Anfang wird ein default-Wert mitgegeben)

```
let mySubject = CurrentValueSubject<String, Never>("")
mySubject.send("Hello")
mySubject.send("World!")
```

![][image-3]
### Werte von einem anderen Publisher empfangen und weiterleiten

```swift

mySubject.subscribe([1,2,3,4,5].publisher) // Weil dieser Publisher am Ende die Pipeline terminiert, wird auch mySubject terminiert
```

=\> Siehe auch Kapitel „Publisher Mergen“

### Ein Subject als Publisher zurückgeben

- Oftmals arbeitet man in einer Funktion intern mit einem Subject, gibt dann aber als Rückgabewert nur den unveränderbaren Publisher zurück

```swift
return mySubject.eraseToAnyPublisher() // -> AnyPublisher<Int, Never>
```


## Subscriber / Subscription ⬇️

- Am Ende der Kette steht häufig ein Subscriber
- Ein Subscriber nimmt die publizierten Werte entgegen und macht etwas damit
- Beispiele sind zum Beispiel `assign` oder `sink`. Das sind Subscriber. Sie geben eine Subscription zurück (AnyCancellable):

```swift
var cancellable: Cancellable? = publisher1.sink { value in
	print("Received value from publisher1: \(value)")
}

//Wenn man die Subscription nicht mehr braucht kann man es so beenden:
object?.cancellable.cancel()
```

Siehe auch: [Cancellable Subscription][1]

##  Hinweis
- Das System enthält meistens schon alle Publisher, Subjects, Subscribers und Operators welche man benötigt um eine Pipeline zu bauen. Man kann aber auch eigene Varianten davon implementieren.

##  Zusammenfassung
- Was macht ein Publisher?
- Was ist ein Subject?
- Welche zwei Arten von Subject existieren?
- Was ist ein Subscriber / was ist eine Subscripton

[1]:	ulysses://x-callback-url/open?id=JwDVjPOLmGhz3HHJ8owI2g

[image-1]:	assets/Combine-Rollen.drawio.png
[image-2]:	assets/2024-02-27%2008.04.41.gif
[image-3]:	assets/2024-02-27%2008.05.54.gif

#learning unit# #guide