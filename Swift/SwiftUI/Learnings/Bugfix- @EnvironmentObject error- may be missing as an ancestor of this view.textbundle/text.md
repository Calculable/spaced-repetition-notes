# Bugfix: @EnvironmentObject error: may be missing as an ancestor of this view
🐞

##  Problem
- Es scheint sich um einen Fehler in SwiftUI zu handeln
- Obwohl ein Environment-Object mitgegeben wurde, hat man darauf in einem Sheet keinen Zugriff
- Bei mir ist das Problem nur auf MacOS aufgetreten

##  Lösung

Statt das Environment-Object nur der Content-View mitzugeben:

```swift
ContentView()
	.environmentObject(dataController)
```

…gibt man es **erneut** auch direkt an das Sheet weiter:

```swift
.fullScreenCover(isPresented: $showingBuyProSheet) {
	UnlockView()
		.environmentObject(unlockManager) 
}
```

##  Zusammenfassung
- Was ist das Problem und wie wird es behoben?