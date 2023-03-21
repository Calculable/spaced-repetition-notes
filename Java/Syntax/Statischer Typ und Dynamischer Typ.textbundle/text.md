# Statischer Typ und Dynamischer Typ
🚙

- Wird ein Objekt als Parameter übergeben, spielt für das Overloading der statische Typ eine Rolle
- Wird eine Methode auf einem Objekt aufgerufen, spielt für das Overriding der dynamische Typ eine Rolle


Beispiel:

```swift
class Sub extends Base {
	void copyTo(Base Other) {} //Methode 1
	void copyTo(Sub other) {} //Methode 2
}
```

```swift
Base b = new Sub()
b.copyTo(b) //Hier wird methode 1 aufgerufen
```


## Zusammenfassung
- Wann spielt der statische Typ und der dynamische Type eine Rolle?

#learning unit#