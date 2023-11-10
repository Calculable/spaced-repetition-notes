# Delegation Pattern
🍷

```swift
protocol DiceGameDelegate: AnyObject {
    func gameDidStart(_ game: DiceGame)
    func game(_ game: DiceGame, didStartNewTurnWithDiceRoll diceRoll: Int)
    func gameDidEnd(_ game: DiceGame)
}
```

Beachte: AnyObject wird verwendet. So kann man später wo das Delegate benötigt wird `weak` verwenden:

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

## Zusammenfassung
- Beispiel (z.B Dice Game)
- Zu was sollte das Protokoll konform sein?

#learning unit#