# Beim Debuggen herausfinden um welche View es sich handelt

Control-click the view in question and choose Print Description in the contextual menu:

```swift
<UIView: 0x7fbec8508420; frame = (30 34; 163 117); autoresize = RM+BM; 
    layer = <CALayer: 0x6000019c65c0>>
```

Often that will be enough to identify the view. If it isn't, you can ask the view questions, though the syntax is a little tricky:

Hier wird zum Beispiel nach der Hintergrundfarbe gefragt:

```swift
(lldb) expr -l objc -O -- [(UIView*)0x7fbec8508420 backgroundColor]
```

```swift
<UIDynamicModifiedColor: 0x6000017c6f10; contrast = normal, 
    baseColor = <UIDynamicSystemColor: 0x6000019c6600; name = systemYellowColor>>
```


#learning unit#