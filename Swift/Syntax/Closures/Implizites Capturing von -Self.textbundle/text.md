# Implizites Capturing von "Self"
🦋

##  Verhalten
- Closures in Swift haben implizit / per default starke Referenzen auf die Verwendeten Objekte. In einigen Fällen ist das ok, in anderen Fällen muss man aufpassen dass man keinen Retain Cycle bekommt, wobei sich zwei objekte gegenseitig stark referenzieren.

## Wann ist strong capturing (meistens) ok?

### 1. Bei Non-Escaping Closures:

Weil diese ja sofort ausgeführt werden

```swift
func doSomething() {
	let closure = {
		print(self.property) // Implicit capture of strong self
    }
    closure()
}
```

### 2. Bei Tasks / Main Actor

Weil die Starke Referenz automatisch freigegeben wird wenn der Task fertig ist oder der Task-Kontext nicht mehr existiert.

```swift
func doSomething() {
	Task {
		print(self.property) // Implicit capture of strong self
    }
}
```

das gleiche filt auch hier:

```swift
func doSomething() {
	MainActor.run {
		print(self.property) // Implicit capture of strong self
    }
}
```

###  3. Bei UIView.animate 

```swift
UIView.animate(withDuration: 1.0, animations: {
	view.alpha = 0
})
```

- Es gibt weitere Fälle die hier nicht aufgeführt sind.



## Wann ist strong capturing nicht ok?

- Wenn man nicht aufpasst kann das zu Reference Cycles führen
- Beispiel für eien Bug: Man captured "Self" implizit in einem Task und weisst den Task dann wiederum einem Property in "self" zu, dann hat man einen retain cycle
- Weiteres Beispiel: Ein Task der potentiell unendlich lange läuft:

```swift
Task {
	for await value in myAsyncSequence {
		handle(...)
	}
}
```

## Siehe auch
Siehe auch: [ulysses://x-callback-url/open?id=irCym2NB\_-eyPMYGRsZ9pg][1]


## Zusammenfassung
- Fälle, in denen Strong Capturing meistens ok ist
- Beispiel mit Task, wie es trotzdem zu einem Bug führen kann

[1]:	ulysses://x-callback-url/open?id=irCym2NB_-eyPMYGRsZ9pg

#learning unit#