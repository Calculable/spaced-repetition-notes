# Fighter Jet Problem
🛩️

## Kurzzusammenfassung in Pseudocode

```swift
protocol A {
	func test()
}

extension A {
	func test() {...}
}

//Die Klasse kann die Extension nur überschreiben, weil test im Protokoll definiert ist.
struct A: B {
	func test() {...}
}
```

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

Es wäre besser gewesen, mit **Constrained Extensions** zu arbeiten


```swift
extension Fighter {
	func eject() {
		print("Bye!")
	}
}

extension Fighter where Self: Rebel {
	func eject() {
		print("Nope!")
	}
}

struct XWing: Fighter, Rebel{}
```



## Zusammenfassung
Was ist das Problem?
Was ist das Fazit?



#learning unit#