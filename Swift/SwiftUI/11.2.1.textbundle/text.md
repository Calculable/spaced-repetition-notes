
# NavigationSplitView 🧭

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

##  Weitere Informationen

Man kann auch programmatisch die Sichtbarkeit der Sidebar steuern: [How to hide and show the sidebar programmatically - a free SwiftUI by Example tutorial (hackingwithswift.com)]()(https://www.hackingwithswift.com/quick-start/swiftui/how-to-hide-and-show-the-sidebar-programmatically)


Man für die einzelnen Spalten auch eigene Grössen vergeben: [How to customize a view’s width in NavigationSplitView - a free SwiftUI by Example tutorial (hackingwithswift.com)]()(https://www.hackingwithswift.com/quick-start/swiftui/how-to-customize-a-views-width-in-navigationsplitview)

So kann man zudem die anzeige noch genauer steuern: [How to customize the display mode of NavigationSplitView - a free SwiftUI by Example tutorial (hackingwithswift.com)]()(https://www.hackingwithswift.com/quick-start/swiftui/how-to-customize-the-display-mode-of-navigationsplitview)


##  Zusammenfassung
- Wie macht man ein 2- oder 3-Spaltiges Layout?
- ohne weitere Informationen



[1]:	https://developer.apple.com/documentation/swiftui/navigationsplitview


[image-1]:	assets/DraggedImage.tiff
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-01-17%20um%2018.45.25.png

#nur learning unit#