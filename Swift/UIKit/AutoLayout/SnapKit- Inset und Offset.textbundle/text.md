# SnapKit: Inset und Offset
🫰

## Codebeispiel
```swift
make.edges.equalTo(superview).inset(UIEdgeInsets(top: 5, left: 10, bottom: 15, right: 20))
make.top.equalTo(superview).offset(100)
```

## Unterschied zwischen Inset und Offset

- Durch `Inset` wird das Element mit dem Constraint immer kleiner

```swift
subview2.snp.makeConstraints { make in
    make.top.leading.bottom.equalToSuperview().inset(20)
    make.top.leading.trailing.equalToSuperview().inset(10)
}
```

![][image-1]

- `Offset` bedeutet hingegen immer "zur Koordinate dazuzählen". Für den Trailing-Edge verwendet man deshalb in der Regel einen negativen Offset zum Parent:

```swift
subview2.snp.makeConstraints { make in
    make.top.leading.bottom.equalToSuperview().offset(20)
    make.trailing.equalToSuperview().offset(10)
}
```

![][image-2]

## Zusammenfassung
- SnapKit Constraint: Wie macht man ein Inset und Offset
- Was ist der Unterschied zwischen Inset und Offset


[image-1]:	assets/Bildschirmfoto%202023-12-04%20um%2017.20.30.png
[image-2]:	assets/Bildschirmfoto%202023-12-04%20um%2017.21.36.png

#learning unit#