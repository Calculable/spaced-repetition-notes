# Projektorganisation: Zwei Ansätze
🗂️

## Ansatz 1: technisch

- UltimatePortfolioApp.swift
- Models
- Views
- Controllers
	- DataController.swift
- Extensions
	- Bundle-Decodable.swift
	- Sequence-Sorting.swift
	- Color-Additions.swift
- Localization
	- Localizable.strings
	- Localizable.stringsdict
	- Awards.json
- Configuration
	- UltimatePortfolio.entitlements
	- Info.plist
	- Main.xcdatamodeld

### Hinweis: Konfigurationen verschieben

- Projekt im Projekt Navigator auswählen
- Target auswählen
- Build Setting
- Filter: Entitlements
	- Pfad bei Code Signing Entitlements anpassen
- Filter: Info.plist
	- Pfad anpassen

## Ansatz 2: inhaltlich

- UltimatePortfolioApp.swift
- DataController.swift
- Extensions
	- ...
- Activities
	- ContentView.swif
	- Home
		- HomeView.swift
		- ItemListView.swift.
	- Projects
		-   ProjectsView.swift
		-   SelectSomethingView.self
		-   ProjectHeaderView.swift
		- ...
	- Awards
		-   AwardsView.swift
		-   Award.swift
		-   Awards.json


Man kann auch noch weitere Gruppen machen, zum Beispiel für Protokolle, UIKit/AppKit Wrappers oder wiederverwendbare Views.

## Zusammenfassung
- Welche zwei Varianten gibt es, um das Projekt zu strukturieren?

#learning unit#