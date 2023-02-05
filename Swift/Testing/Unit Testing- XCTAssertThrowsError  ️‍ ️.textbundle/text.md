# Unit Testing: XCTAssertThrowsError 👁️‍🗨️

```swift
XCTAssertThrowsError(try functionThatThrows()) { error in
	XCTAssertEqual(error as! MyError, MyError.xy)
}
```
