# Delegation Pattern
::19::

```swift
protocol DiceGameDelegate: AnyObject {
    func gameDidStart(_ game: DiceGame)
    func game(_ game: DiceGame, didStartNewTurnWithDiceRoll diceRoll: Int)
    func gameDidEnd(_ game: DiceGame)
}
```


```swift
class DiceGame {
	weak var delegate: DiceGameDelegate?
	func play() {
		delegate?.gameDidStart(self)
		//...
		delegate?.game(self, didStartNewTurnWithDiceRoll: diceRoll)
	    //...
		delegate?.gameDidEnd(self)
	}
}
```

Beachte: Das Delegate ist optional
