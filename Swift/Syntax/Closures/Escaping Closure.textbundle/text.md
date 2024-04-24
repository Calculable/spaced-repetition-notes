# Escaping Closure
📞

## @Escaping Closure

- wenn man ein closure übergibt und dies nicht sofort verwendet wird, dann kennzeichnet man es mit `@Escaping`


##  Beispiel

```swift
// Function that accepts an escaping closure and assigns it to the property
func onComplete(_ closure: @escaping () -> Void) {
	completionClosure = closure
}
```


## Hintergrund: Wann ist ein Closure "Escaping"?

- Wenn es als Parameter einer Funktion übergeben wird aber ausserhalb der Funktion aufgeruen (normalerweise wenn es irgendwo gespeichert wird um es später aufzurufen)
- Wenn eine Funktion eine andere Funktion zurückgibt (Higher Order Functions)


- Man muss das angeben für das Memory Management des Systems

## Diese Regeln werden durch den Compiler "entforced":

![][image-1]

![][image-2]


![][image-3]

## Zusammenfassung
Escaping Closure

[image-1]:	assets/Bildschirmfoto%202024-01-08%20um%2017.04.42.png
[image-2]:	assets/Bildschirmfoto%202024-01-08%20um%2017.02.51.png
[image-3]:	assets/Bildschirmfoto%202024-01-08%20um%2017.04.27.png

#learning unit#