# Auswirkung von greaterThanOrEqualTo / lessThanOrEqualTo Constraints
↔️

## Fazit

Beisipel: 

```swift
make.height.lessThanOrEqualTo(200)
```

**Fall 1: Die View hat eine Intrinsic Content Size von unter 200**: Der Constraint sagt NICHT, dass man eine Höhe von 200 preferiert. Es wird die Intrinsic Content Size bevorzugt

**Fall 2: Die View hat eine Intrinsic Content Size von über 200**: Die View wird auf eine Höhe von 200 geschrumpft

**Fall 3: Die View hat keine Intrinsic Content Size**: Auch wenn es keine Intrinsic Content Size gibt, wird nicht automatisch 200 als Höhe preferiert. Dazu müsste man stattdessen so etwas schreiben

##  Details: Fallbeispiel


### Fall 1

Man hat eine View mit dieser intrinsic content size:

```swift
override var intrinsicContentSize: CGSize {
    return CGSize(width: 100, height: 100)
}
```

Auf der View setzt man die folgenden Constraints:

```swift
customView.snp.makeConstraints { make in
    make.centerX.centerY.equalToSuperview()
    make.height.lessThanOrEqualTo(200)
}
```

Resultat:  Die Intrinsic Content Size wird nicht verändert, wenn der Constraint damit bereits erfüllt ist. Selbst dann nicht, wenn die Content Hugging Priority oder Content Compression Resistance sehr tief ist

![][image-1]

### Fall 2

Man hat eine View mit dieser intrinsic content size:

```swift
    override var intrinsicContentSize: CGSize {
        return CGSize(width: 100, height: 300)
    }
```

Auf der View setzt man die folgenden Constraints:

```swift
customView.snp.makeConstraints { make in
    make.centerX.centerY.equalToSuperview()
    make.height.lessThanOrEqualTo(200)
}
```

Resultat: Die View wird geschrumpft auf 200:

![][image-2]

### Fall 3

Man hat eine View mit dieser intrinsic content size:

```swift
    override var intrinsicContentSize: CGSize {
        return CGSize(width: 100, height: UIView.noIntrinsicMetric)
    }
```

Auf der View setzt man die folgenden Constraints:

```swift
customView.snp.makeConstraints { make in
    make.centerX.centerY.equalToSuperview()
    make.height.lessThanOrEqualTo(200)
}
```

Resultat: Die View wird NICHT auf 200 hochgezogen:

![][image-3]

Wenn man so etwas möchte müsste man es so schreiben:

```swift
customView.snp.makeConstraints { make in
    make.centerX.centerY.equalToSuperview()
    make.height.lessThanOrEqualTo(200)
    make.height.equalTo(200).priority(.low)
}
```


Das gleiche Beispiel mit `greaterThanOrEqualTo(200)` würde zwar so aussehen, das Layout ist aber nicht eindeutig. Man kann also nicht davon ausgehen, dass es funktioniert

![][image-4]

## Zusammenfassung
Man setzt auf einer View einen Constraint: height.lessThanOrEqualTo(200). Was geschieht in den folgenden Fällen:
-Fall 1: Die View hat eine Intrinsic Content Size von unter 200
-Fall 2: Die View hat eine Intrinsic Content Size von über 200
-Fall 3: Die View hat keine Intrinsic Content Size

[image-1]:	assets/simulator_screenshot_8BE7C333-98A3-4756-8431-0B8495308868.png
[image-2]:	assets/simulator_screenshot_A965F4FA-F34E-43F3-A600-62B26CE83F2E.png
[image-3]:	assets/simulator_screenshot_265862E0-7C3B-4406-AA8A-D2FFDBA04D25.png
[image-4]:	assets/simulator_screenshot_14C55876-9063-4FE2-A0B7-195938ECAF53.png

#learning unit#