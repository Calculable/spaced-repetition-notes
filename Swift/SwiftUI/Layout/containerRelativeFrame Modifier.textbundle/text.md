# .containerRelativeFrame Modifier
🖼️
Wie bei einem Boostrap-Grid kann man damit aufteilen, wie gross die Items im Verhältnis zu ihrem Parent sein sollen:

In diesem Beispiel 5/12:

```swift
ScrollView(.horizontal, showsIndicators: false) {
    HStack {
        ForEach(0..<10) { i in
            Text("Hello World")
                .containerRelativeFrame(.horizontal, count: 12, span: 5, spacing: 10, alignment: .center)
                .background(.green)
        }
    }
}
```

![][image-1]


##  Zusammenfassung
- Was kann man damit machen? (nicht den genauen Code)

[image-1]:	assets/2023-06-18%2007.09.16.gif

#learning unit# #iOS17