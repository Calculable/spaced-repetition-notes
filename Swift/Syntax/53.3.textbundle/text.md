# Asynchronen Code mit Callback testen 👁️‍🗨️
::53.2::

> When your asynchronous code completes you call  `fulfill()`  on it to mark it as complete, and you can then call some variant of  `XCTAssert()`  to check whether the test succeeded or failed.

```swift
func testStoryLoading() throws {
    let parser = FeedParser()

    // create the expectation
    let exp = expectation(description: "Loading stories")

    // call my asynchronous method
    parser.loadStories {
        // when it finishes, mark my expectation as being fulfilled
        exp.fulfill()
    }

    // wait three seconds for all outstanding expectations to be fulfilled
    waitForExpectations(timeout: 3)

    // our expectation has been fulfilled, so we can check the result is correct
    XCTAssertEqual(parser.stories.count, 20, "We should have loaded exactly 20 stories.")
}
```


## Zusammenfassung
- Codebeispiel
