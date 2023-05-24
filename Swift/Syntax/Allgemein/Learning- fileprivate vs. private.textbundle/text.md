# Learning: fileprivate vs. private
🔒

## Private
- Extensions im gleichen File können darauf zugreifen
- Extensions in einem anderen File können nicht darauf zugreifen!

## Fileprivate

- Extensions im gleichen File können darauf zugreifen (wie bei Private)
- Extensions in einem anderen File können nicht darauf zugreifen! (wie bei Private!)

## Was ist der Unterschied?
- Auf `fileprivate` kann man auch aus einem anderen Struct / Klasse zugreifen, selbst wenn es keine Extension ist!

```swift
struct A {
    private var privateVar = 0
    fileprivate var fileprivateVar = 1
}

struct B {
    let a: A

    func do() {
        print(a.privateVar) //Fehler 💥
        print(a.fileprivateVar) //Erlaubt ✅
    }
}
```

=\> `fileprivate` ist also weniger restriktiv.
 
## Zusammenfassung
- Was ist der Unterschied?
- Wie funktioniert Fileprivate?

#learning unit#