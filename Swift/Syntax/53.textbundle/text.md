# Unit Testing Testgerüst 👁️‍🗨️
::53::

## Testgerüst

```swift
class TowerInstanceTests: XCTestCase {
  var subject: Tower!
  
  override func setUp() {
 	super.setUp()
    subject = Tower(name: "Empire State Building", city: "New York City", country: "USA", height: 381, yearBuilt: 1931, latitude: 40.748457, longitude: -73.985525)
  }
  
  override func tearDown() {
	super.tearDown()
    subject = nil
  }

  override class func setUp() { //wird nur einmal aufgerufen
	super.setUp()
  }
	
  override class func tearDown() {
	super.tearDown()
  }
}
```

##  Testfunktionen
- Test-Funktionen haben das Prefix `text`

## Zusammenfassung
- Testklasse (Protokoll)
- Einfache Testfunktion
