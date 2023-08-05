# Main Actor
🤴

- Es geht darum, dass alle Änderungen, die eine Auswirkung auf das UI haben, im Main Actor geschehen müssen
- In der Regel sorgt man dafür, dass der ganze View / ViewModel Code im Main Actor läuft. 
- Manchmal ist es aber nötig, den Main-Actor explizit aufzurufen. Zum Beispiel wenn man libraries hat, welche einen Closure entgegennehmen und diesen dann in einem anderen Kontext ausführen: 

```swift
await MainActor.run {
    // your work here
}

//früher: DispatchQueue.main.async
```

- Man kann auch Werte zurückgeben
- Man kann auch Funktionen oder Klassen oder Properties oder Closures mit `@MainActor` auszeichnen. So wird sichergestellt, dass es nur auf dem Main-Thread aufgerufen werden darf:


```swift
@MainActor
func display(scene: Scene)
```

```swift
@MainActor var images: [UIImage] = []
```

```swift
func updateData(completion: @MainActor @escaping () -> ()) 
	//...
}
```

## Zusammenfassung
- Zweck / Anwendungsfall
- Aufruf

#learning unit#