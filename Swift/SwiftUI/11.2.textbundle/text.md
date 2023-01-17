# NavigationStack 🧭

## Navigation Stack löst die NavigationView ab

> If your app has a minimum deployment target of iOS 16, iPadOS 16, macOS 13, tvOS 16, or watchOS 9, or later, transition away from using `NavigationView`- In its place, use `NavigationStack`and `NavigationSplitView` instances

## Bei 1-Spalten Layout (Stack)

Vorher:
```swift
NavigationView {

}.navigationViewStyle(.stack)
```

Nachher:

```swift
NavigationStack { /* content */}
```

Darin kann ich ganz normal navigation Links platzieren

## Bei 2-Spalten Layout (Übersicht und Detail)


Vorher:

```swift
NavigationView {
	// This is deprecated.
	/* column 1 */
	/* column 2 */
}
```

Nachher:

```swift
NavigationSplitView {
	/* column 1 */
} detail: {
	/* column 2 */
}
```

Was unter „detail“ eingetragen ist kann je nach gerät Initial dargestellt werden, es wird jedoch überschrieben, wenn man einen Navigation Link anklickt

![][image-1]

## Bei 3-Spalten Layout

Vorher\_:

```swift
NavigationView { // This is deprecated. /* column 1 */ /* column 2 */ /* column 3 */}
```

```swift
NavigationSplitView { 
	/* column 1 */
} content: { 
	/* column 2 */
} detail: {
	/* column 3 */
}
```

> If you need navigation within a column, embed a navigation stack in that column. This arrangement provides finer control over what each column displays.  [`NavigationSplitView`][1]  also enables you to customize column visibility and width.
![][image-2]
## ToDo: Ausprobieren

- Todo: Programmatic Navigation

## Zusammenfassung
- Wie macht man ein Ein-Spaltiges Layout, ein Zwei-Spaltiges Layout und ein Drei-Spaltiges Layout?

[1]:	https://developer.apple.com/documentation/swiftui/navigationsplitview

[image-1]:	assets/DraggedImage.tiff
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-01-17%20um%2018.45.25.png

#nur learning unit#