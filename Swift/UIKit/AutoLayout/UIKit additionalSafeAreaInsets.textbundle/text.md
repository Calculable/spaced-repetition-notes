# UIKit additionalSafeAreaInsets
🖼️


## Zweck
- Manchmal hat man eigene Views die sich wie eine Safe Area verhalten sollen
- Hier zum Beispiel liegt ein Teil der blauen View hinter den roten Views:
![][image-1]

Deshalb kann man die Safe Area erweitern:

```swift
.additionalSafeAreaInsets = ...
```

## Siehe auch

- UIKit Safe Area Layout Guide: [ulysses://x-callback-url/open?id=Q2ykhU9a8GYyXGBpgRPmgw][1]

## Quelle

> [https://developer.apple.com/documentation/uikit/uiview/positioning\_content\_relative\_to\_the\_safe\_area][2]

## Zusammenfassung
- Zweck

[1]:	ulysses://x-callback-url/open?id=Q2ykhU9a8GYyXGBpgRPmgw
[2]:	https://developer.apple.com/documentation/uikit/uiview/positioning_content_relative_to_the_safe_area

[image-1]:	assets/Bildschirmfoto%202023-07-26%20um%2017.30.02.png

#learning unit#