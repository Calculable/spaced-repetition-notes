# Networking mit Combine
👭

## Was ist Combine?

- Ein Wrapper um URL Session

```swift
import Combine
```

## Beispiel

```swift
@State private var requests = Set<AnyCancellable>()

URLSession.shared.dataTaskPublisher(for: url)
    .map(\.data)
    .decode(type: User.self, decoder: decoder)
    .replaceError(with: User.default)
    .sink({ /*$0*/  })
    .store(in: &requests)
```

- Die einzelnen Schritte heissen "Operators"

## Was geschieht hier?

- `dataTaskPublisher` ist die Combine-Variante von `dataTask(with:)`
- `map` dient hier dazu, nur die Response zu lesen und nicht den Response-Status.
- Falls ein Error auftritt, wird einfach ein Default-Objekt zurückgegeben
- Mit dem `sink` kann man beliebigen Code ausführen, wenn die Pipeline zu ende ist

## Warum hat man das Set mit Requests gespeichert?

> If you didn't store the `AnyCancellable` somewhere, the network request would be cancelled immediately, because the `AnyCancellable` returned by `sink(receiveValue:)` would be deallocated at the end of the function scope.

> So, in summary, the `@State private var requests = Set<AnyCancellable>()` is needed to keep the network requests alive for the duration of the view's lifetime.

## Zusammenfassung
- Was ist Combine
- Wie sieht ein Request mit Combine ungefähr aus? (vor allem Konzept)


#learning unit#