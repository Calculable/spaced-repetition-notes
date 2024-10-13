# Unterschied zwischen DispatchQueue.main.async, MainActor.run und Task @MainActor
🤔


```swift
//Beachte: Wird ohne await aufgerufen
DispatchQueue.main.async {
	//Await nicht möglich
} 

//Hier geht es direkt weiter, bevor MainActor-Code  ausgeführt wurde
```

```swift
await MainActor.run {
	//Await nicht möglich
}

//Hier geht es erst weiter, wenn der MainActor-Code ausgeführt wurde
```

Hier kann man hingegen await verwenden:

```swift
Task { @MainActor in
	//Hier kann man await verwenden
	await xy.doSomehting()
}
```

Siehe auch: [ulysses://x-callback-url/open?id=BZzVxsLhifbJF3logXbYfA][1]

##  Zusammenfassung
- Was ist der Unterschied zwischen den drei Varianten?

[1]:	ulysses://x-callback-url/open?id=BZzVxsLhifbJF3logXbYfA

#learning unit# #guide