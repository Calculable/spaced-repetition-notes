
# Fighter Jet Problem
::15::

## Beispiel
Es geht um die Kombination von Protocol und Protocol Extension:

```swift
protocol Fighter {
	func eject()
}

extension Fighter {
	func eject() {
		print("Bye!")
	}
}

struct XWing: Fighter {
	func eject() {
		print("Nope!")
	}
}

func destroy(_ fighter: Fighter) {
	figther.eject()
}
```

**Jetzt liefert das folgende Codebeispiel „Nope“ ::!::**

```swift
let red5 = XWing()
destroy(red5) //nope
```

**Wenn man hingegen die eject-Methode aus dem Protokoll streicht, dann wird „Bye“ zurückgegeben:**

```swift
protocol Fighter() {}
```

```swift
let red5 = XWing()
destroy(red5) //bye!
```


## Fazit

- Wenn man die Methode in das Protokoll aufnimmt, dann kann die Extension von der Klasse überschrieben werden. Ansonsten nicht.



