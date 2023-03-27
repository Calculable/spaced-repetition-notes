# Async Overloading

=\> Man macht Gleichnamige Sync- und Async-Funktionen.

> If you have async and synchronous functions that can be called in the same way, Swift will prefer whichever one matches your current context – if the call site is currently async then Swift will call the async function, otherwise it will call the synchronous function.

This point is important, because it allows library authors to provide both synchronous and asynchronous versions of their code without having to name the async functions specially.

Das ist vor allem für Entwickler interessant, die Backwards-Kompatible API’s anbieten wollen

```swift
func doSomething() async throws -> String {
    
}

func doSomething() throws -> String {
   
}
```

##  Zusammenfassung
- Wie kann man sowohl eine Synchrone als auch eine Asynchrone Version des gleichen Codes anbieten?

#learning unit#