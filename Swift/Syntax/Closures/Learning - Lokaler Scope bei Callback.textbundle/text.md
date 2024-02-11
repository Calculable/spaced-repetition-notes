# Learning - Lokaler Scope bei Callback
🧠
```swift
class SomeClass {
	private func doSomething {
		MyHelper().doANetworkingTask()
	}
}
```

```swift
class MyHelper {
	private func doSomething() {
		doSomeNetworking(callback: { [weak self] result in
			//self will be nil here
		})
	}
}
```

##  Zusammenfassung

Was ist hier heikel? -\> MyHelper().doANetworkingTask()

#learning unit#