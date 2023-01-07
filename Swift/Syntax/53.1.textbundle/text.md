# Unit Testing XCT Funktionen 👁️‍🗨️
::53.1::

## XCTUnwrap

Wirf einen Fehler wenn es Nil ist

```swift
    let token = try XCTUnwrap(user.getAuthenticationToken())
```

## XCTAssertEqual

Kann auch mit Optionals verwendet werden:

```swift
XCTAssertEqual(user.getAuthenticationToken()?.count, 40)
```

## XCTAssertTrue

```swift
    XCTAssertTrue(result, "Image generation should complete successfully.")
```

## XCTFail

`XCTFail()`

## XCTAssertThrowsError

```swift
XCTAssertThrowsError(try functionThatThrows()) { error in
	XCTAssertEqual(error as! MyError, MyError.xy)
}
```


## Zusammenfassung
- Unwrap
- Equal
- True
- Fail
- Throws
