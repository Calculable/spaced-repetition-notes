# Task captures self implicitly
🦋

## Verhalten
Im Gegensatz zu den meisten Closures wird bei einem Task `self` implizit „captured“. Hier wird zum Beispiel `self` implizit Captured, weil handle zur entsprechenden Klasse gehört. 

```swift
Task {
   handle(...)
}
```

##  Problem

Das kann ein Problem sein, wenn man einen Task hat der potentiell Unbegrenzt läuft (=\> Memory Leak weil self nie fregegeben werden kann):

```swift
Task {
	for await value in myAsyncSequence {
		handle(...)
	}
}
```


## Lösung
Aber man kann das Problem so beheben:


```swift
Task { [weak self] in
	for await value in myAsyncSequence {
		guard let self else {return}
		handle(...)
	}
}
```

## Falsche Lösung!

Achtung, hier würde das Problem nicht gelöst!


```swift
Task { [weak self] in
	guard let self else {return}
	for await value in myAsyncSequence {
		handle(...)
	}
}
```

##  Zusammenfassung
- Wie kann man in einem Task auf `self` Zugreifen
- Was für ein Problem kann entstehen?
- Wie kann man das Problem lösen?

#learning unit#