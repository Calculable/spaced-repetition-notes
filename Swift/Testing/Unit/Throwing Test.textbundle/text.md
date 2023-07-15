# Throwing Test
💥

##  Try! vs. throwing test

- Wenn man `try!` verwendet und der Test fehlschlägt, dann crasht der gesamte Test-Prozess
- Wenn man jedoch `try` in einem throwing test verwendet, dann schlägt nur der Test fehl:

```swift
func testXY() throws {
	try doSomething()
}
```

## Zusammenfassung
- Was ist der unterschied zwischen „try!“ und einem throwing test?

#learning unit#