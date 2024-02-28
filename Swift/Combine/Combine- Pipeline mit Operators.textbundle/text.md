# Combine: Pipeline mit Operators
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

## Beispiel: Flat Map
- Wenn ein Publisher einen einen Wert transformiert und das Resultat ein anderer Publisher ist, kann man `flatMap` verwenden damit man nur die Daten empfängt und nicht publisher Instanzen:

```swift
let xy = URLPublisher.flatMap { requestURL in
	URLSession.shared
		.dataTaskPublisher(for: requestURL)
	}
}
```

## Beispiel: Mit einem Property weiterarbeiten

```swift
publisher //publisher of MyClass
	.publisher(for: \.title) //publisher of String
```

##  Weitere Operators

![][image-1]

## Zusammenfassung
- Wie kann man mit Combine Pipelines bauen? (ohne Details)

[image-1]:	assets/Bildschirmfoto%202024-02-21%20um%2015.49.20.png

#learning unit#