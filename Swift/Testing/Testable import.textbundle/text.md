# Testable import
🧐

Damit kann auf alle Teile des Projektes zugreifen, ohne diese als `public` markieren zu müssen.


```swift
import CoreData
import XCTest
@testable import UltimatePortfolio

class BaseTestCase: XCTestCase {
```

## Zusammenfassung
- Wie macht man einen Testable import und was bringt das?

#nur learning unit#