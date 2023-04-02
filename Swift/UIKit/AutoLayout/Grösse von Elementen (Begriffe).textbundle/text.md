# Grösse von Elementen (Begriffe)
↕️

## Theorie

- **Intrinsic Content Size**: "die natürliche Grösse"

> Wenn man eine Intrinsic Content Size hat (wie bei einem Label) dann muss man Height und Width nicht festlegen. Beachte: Text-Länge kann sich ändern und auch die Text-Grösse


- **Content Compression Resistance**: wir stark will das Objekt nicht kleiner werden
- **Content Hugging**: wie stark will das Objekt nicht wachsen


##  Beispiel

![][image-1]


## Default Werte
- 750 ist de Default Priority für Content Compression
- 250 ist die Default Priority für Content Hugging

Das heisst: Die Elemente werden standartmässig gerne „gestreched“ aber ungerne „compressed“

##  Manchmal setzt man die Grösse im Code

```swift
cluesLabel.setContentHuggingPriority(UILayoutPriority(1), for: .vertical)
```

Dann kann man in Xcode die Intrinsic Size für den Platzhalter angeben damit es in der Vorschau gut aussieht:

![][image-2]

## Zusammenfassung
- Begriff für "natürliche Grösse"
- Begriff für "wir stark will es nicht wachsen"
- Begriff für "wie stark will es nicht schrumpfen"

[image-1]:	assets/Bildschirmfoto%202021-09-11%20um%2012.54.21.png
[image-2]:	assets/Bildschirmfoto%202021-09-11%20um%2012.56.52.png

#learning unit#