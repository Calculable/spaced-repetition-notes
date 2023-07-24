# Combine: Pipeline
🔀

## Eine Pipeline aufsetzen

- Jeder Operator gibt einen neuen Publisher zurück
- Operatoren kann man aneinander hängen

```swift
let publisher1 = PassthroughSubject<Int, Never>()

let publisher2 = publisher1
	.map { value in
		value + 100
	}
	.filter {
		($0 % 2) == 0
	}
```

- Wenn man jetzt Werte in den `Publisher1` gibt, kommen sie bei `Publisher2` transformiert heraus.

## Flat Map
- Wenn ein Publisher einen einen Wert transformiert und das Resultat ein anderer Publisher ist, kann man `flatMap` verwenden damit man nur die Daten empfängt und nicht publisher Instanzen:

```swift
let xy = URLPublisher.flatMap { requestURL in
	URLSession.shared
		.dataTaskPublisher(for: requestURL)
	}
}
```

## Completion

### Mit letztem Wert terminieren

```swift
subject.send("Hello!")
subject.send("Hello again!")
subject.send("Hello for the last time!")
subject.send(completion: .finished)
subject.send("Hello?? :(") //wird nicht mehr gesendet
```

### Mit einem Fehler abschliessen

```swift
subject.send(completion: .failure(.somethingWentWrong))
```

## Zusammenfassung
- Wie kann man mit Combine Pipelines bauen? (ohne Details)

#learning unit#