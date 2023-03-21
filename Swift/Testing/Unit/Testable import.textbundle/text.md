# Testable import
🧐

Damit kann auf die Teile des Projektes zugreifen, ohne diese als `public` markieren zu müssen (Vermutung: Zugriff auf Internal, nicht aber auf Private).


```swift
import CoreData
import XCTest
@testable import UltimatePortfolio

class BaseTestCase: XCTestCase {
```

## Zusammenfassung
- Wie macht man einen Testable import und was bringt das?

#learning unit#