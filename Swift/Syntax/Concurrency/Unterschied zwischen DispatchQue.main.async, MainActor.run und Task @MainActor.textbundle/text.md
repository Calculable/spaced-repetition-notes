#  Unterschied zwischen DispatchQue.main.async, MainActor.run und Task @MainActor
🤔


Diese zwei sind praktisch identisch, `MainActor.run {}` ist jedoch empfohlen:

```swift
DispatchQueue.main.async {
	//Await nicht möglich
	//Beachte: Wird ohne await aufgerufen
} 
```

```swift
//empfohlene Variante
await MainActor.run {
	//Await nicht möglich
	
}
```

Hier kann man hingegen await verwenden:

```swift
Task { @MainActor in
	//Hier kann man await verwenden
}
```

Siehe auch: [ulysses://x-callback-url/open?id=BZzVxsLhifbJF3logXbYfA][1]

##  Zusammenfassung
- Was ist der Unterschied zwischen den drei Varianten?

[1]:	ulysses://x-callback-url/open?id=BZzVxsLhifbJF3logXbYfA

#learning unit#