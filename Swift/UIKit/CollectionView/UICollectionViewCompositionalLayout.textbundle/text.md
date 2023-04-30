# UICollectionViewCompositionalLayout
📐

## Was macht ein Layout?

Das Layout definiert, wie Sections und Items dargestellt werden

## Einer Collection View ein Layout zuweisen

```swift
collectionView.collectionViewLayout = createCompositionalLayout()
```

##  Hierarchie

Jedes Element kann jeweils mehrere Einträge des Elements oberhalb enthalten:

![][image-1]

Jede Section kann wieder ein eigenes Layout haben

##  Konzept

- Für jede Item und jede Gruppe kann eine gewünschte Dimension angeben:
	- `.fractional` (im Verhältnis zum Bildschirm)
	- `.estimated` (Um die Intrinsic Content Size zu verwenden)
	- `.absolute` …
- Es ist legitim, dass eine Gruppe nur ein Item hat
- Man kann auch Section-Headers etc. definieren (in diesem Codebeispiel nicht gezeigt)
- Man könnte für jede Section ein anderes Layout machen

## Headers

> In UIKit, by default, collection views have no headers. You can add headers by including a supplementary data array with header titles. Or you can treat the first element in the data array as the header.

(Code mit Headers nicht zusammengefasst)

## (Beispielcode)

(Code beim Lernen ignorieren, hier hat es noch Header und Footer, deshalb ist es unübersichtlich)

```swift
private func createCompositionalLayout() -> UICollectionViewLayout {
        
        func createBasicListSection() -> NSCollectionLayoutSection {
            let itemSize = NSCollectionLayoutSize(widthDimension: .fractionalWidth(1.0), heightDimension: .estimated(300))
            let item = NSCollectionLayoutItem(layoutSize: itemSize)
            
            let groupSize = NSCollectionLayoutSize(widthDimension: .fractionalWidth(1.0),
                                                   heightDimension: .estimated(300))
            
            let group = NSCollectionLayoutGroup.horizontal(layoutSize: groupSize,
                                                           subitems: [item])
            
            let section = NSCollectionLayoutSection(group: group)
            return section
        }
        
        let layout = UICollectionViewCompositionalLayout { sectionIndex, layoutEnvironment in
            //this closure will be called whenever the layout changes (for example landscape and portrait)
            let headerFooterSize = NSCollectionLayoutSize(
                widthDimension: .fractionalWidth(1.0),
                heightDimension: .estimated(20)
            )
            let sectionHeader = NSCollectionLayoutBoundarySupplementaryItem(
                layoutSize: headerFooterSize,
                elementKind: UICollectionView.elementKindSectionHeader,
                alignment: .top
            )
            
            let section = createBasicListSection()
            section.boundarySupplementaryItems = [sectionHeader]
            
            return section
        }
        
        let config = UICollectionViewCompositionalLayoutConfiguration()
        config.interSectionSpacing = 20
        layout.configuration = config
        
        return layout
    }
```

Beachte: Man könnte für jede Section wiederum ein anderes Layout machen.

## Möglicherweise gute Quelle

[How to build a UICollectionView like the App Store - YouTubeYouTubehttps://www.youtube.com › watch][1]


##  Zusammenfassung
- Welche drei Elemente in der Hierarchie gibt es?
- Auf welche drei Arten kann man die Dimension konfigurieren?

[1]:	https://www.google.de/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwi6iqvZwcr-AhWSh_0HHezoAU4QtwJ6BAhHEAI&url=https%3A%2F%2Fwww.youtube.com%2Fwatch%3Fv%3DSR7DtcT61tA&usg=AOvVaw2ghdVa34agGcQWObvaIiZa "How to build a UICollectionView like the App Store - YouTubeYouTubehttps://www.youtube.com › watch"

[image-1]:	assets/DraggedImage.tiff

#learning unit#