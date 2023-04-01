# Warum sind Outlets Implicitly Unwrapped Optionals?
🤔

```swift
@IBOutlet var imageView: UIImageView!
```


=\> Wenn der ViewController geladen wird, ist die View noch nicht verfügbar.
=\> Sobald wir es verwenden, ist es nicht mehr nil.



#learning unit#