# SnapKit: Grundlagen
🫰

## Was wird nicht mehr benötigt
- `translateAutoresizingMaskIntoConstraints` braucht es nicht mehr
- Man muss nicht mehr daran denken, die Constraints zu aktivieren

## Beispiel: Constraints für eine View definieren

```swift
let box = UIView()
superview.addSubview(box)

box.snp.makeConstraints { (make) -> Void in
	make.edges.equalToSuperview().inset(20)
	
	// Alternative
	make.edges.equalTo(superview).inset(UIEdgeInsets(top: 20, left: 20, bottom: 20, right: 20))

	//Alternative
    make.top.equalTo(superview).offset(20)
    make.left.equalTo(superview).offset(20)
    make.bottom.equalTo(superview).offset(-20)
    make.right.equalTo(superview).offset(-20)
}
```

`snp.remakeConstraints` is similar to `snp.makeConstraints`, but will first remove all existing constraints installed by SnapKit.
![][image-1]

Beachte: Der Offset bei Bottom und Right muss negativ definiert werden!

## Anchors
- left, right, top, bottom, leading, trailing
- width, height, centerX, centerY

##  Constraints
Es gibt: `.equalTo`, `.lessThanOrEqualTo`, `.greaterThanOrEqualTo `


##  Zusammenfassung
- Beispiel: Top soll 20 vom Parent entfernt sein
- Was wird nicht mehr benötigt?

[image-1]:	assets/simulator_screenshot_0B5CCB0C-06A8-4A35-A9D9-0C52DCD36143.png

#learning unit#