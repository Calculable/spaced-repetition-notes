# UICollectionViewFlowLayout
🌊
## Was macht ein Layout?

Das Layout definiert, wie Sections und Items dargestellt werden

## Was macht das UICollectionViewFlowLayout

- Je nach Scroll-Richtung werden die Elemente als Zeile oder Spalte angezeigt

![][image-1]


##  (Codebeispiel)

```swift
 override func viewDidLoad() {
     super.viewDidLoad()
     // Do any additional setup after loading the view.
     let flowLayout = UICollectionViewFlowLayout()
     flowLayout.minimumInteritemSpacing = 300
     flowLayout.minimumLineSpacing = 300
     self.collectionView.collectionViewLayout = flowLayout
}
```

![][image-2]

##  Zusammenfassung
- Wie sieht ein UICollectionViewFlowLayout aus? (Primär Bild)

[image-1]:	assets/flow_horiz_headers_2x.png
[image-2]:	assets/DraggedImage.png

#learning unit#