# Semaphore
🚦

## Konzept
- Regelt den Zugriff auf eine geteilte Ressource
- FIFO Prinzip
- Es gibt einen Counter
	- Ist der Counter grösser oder gleich 0 kann man auf die Resource zugreifen, ansonsten muss man Warten
- `wait()` =\> Wir wollen Zugriff auf die Ressource, `counter -= 1`
- `signal()` =\> Wir brauchen die Ressource nicht mehr `counter += 1`

## Codebeispiel
```swift
let firstStepDone = DispatchSemaphore(value: 1)

firstStepDone.wait() //Wenn die Ressource noch nicht verfügbar ist, muss hier gewartet werden, => Wenn der Wert grösser oder gleich 0 ist, darf der Code fortfahren, immer der Thread der am längsten Wartet darf weitermachen- Nicht auf dem Main Thread aufrufen

firstStepDone.signal() //Wir geben die Ressource frei, +1
```

- Wenn wir den initialen Wert auf zwei Setzen, dürften zwei Threads gleichzeitig auf die Ressource zugreifen

## Zusammenfassung
- Konzept, ohne Code (was machen die zwei Funktionen)

#learning unit#