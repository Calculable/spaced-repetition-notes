# Unit Testing
::32::

## Testgerüst

```swift
class TowerInstanceTests: XCTestCase {
  var subject: Tower!
  
  override func setUp() {
    subject = Tower(name: "Empire State Building", city: "New York City", country: "USA", height: 381, yearBuilt: 1931, latitude: 40.748457, longitude: -73.985525)
  }
  
  override func tearDown() {
    subject = nil
  }
}
```

- Test-Funktionen haben das Prefix `text`

## Assert

```swift
XCTAssert(..., "...")
XCTAssertEqual
XCTAssertNoThorws
XCTAssertThorsError
```
