# Binding Missverständnis
🖇️

Ich dachte, dass man Bindings nur verwendet, wenn die View selbst in der Lage sein möchte, den Wert eines Structs anzupassen.

Allerdings kann man Binding auch verwenden, wenn man nur über Änderungen informiert werden möchte.

Beispiel:

```swift
let items: ArraySlice<Item>
```

=\> Hier bekommt man mit, wenn der ganze `ArraySlice` durch einen anderen `ArraySlice` ersetzt wird. Allerdings bekommt man es nicht mit, wenn sich innerhalb des `ArraySlice` ein einzelnes Item verändert.  Hier hingegen schon:

```swift
@Binding var items: ArraySlice<Item>
```


## Zusammenfassung
- Was war mein Missverständnis bezüglich Bindings?


#nur learning unit#