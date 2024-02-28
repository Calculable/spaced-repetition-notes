# Combine: Type Erasure
🔀

Die Typen der Combine-Pipelines können sehr kompliziert werden:

```swift
@Published var password: String = ""
@Published var passwordAgain: String = ""

var validatedPassword: Map<CombineLatest<Published<String>, Published<String>, String?>> {
   return CombineLatest($password, $passwordAgain) { password, passwordAgain in
      guard password == passwordAgain, password.count > 8 else { return nil }
      return password
   } 
   .map { $0 == "password1" ? nil : $0 }
}
```

Mit Type Erasure kann man an den Systemgrenzen den Rückgabewert vereinfachen:


```swift
@Published var password: String = ""
@Published var passwordAgain: String = ""

var validatedPassword: AnyPublisher<String?, Never> {
   return CombineLatest($password, $passwordAgain) { password, passwordAgain in
      guard password == passwordAgain, password.count > 8 else { return nil }
      return password
   } 
   .map { $0 == "password1" ? nil : $0 }
   .eraseToAnyPublisher()
}
```


(`Never` ist der Error-Type)

##  Zusammenfassung
- Wie kann man bei einer Combine-Pipeline den Rückgabetyp vereinfachen?  (Was ist der letzte Operator und der Rückgabewert?)

#learning unit#