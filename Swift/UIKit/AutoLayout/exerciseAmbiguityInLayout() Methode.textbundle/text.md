# exerciseAmbiguityInLayout() Methode
🏋️

- Ambiguity im Layout bedeutet: „Das Layout ist nicht eindeutig“
- Man hat also nicht genügend Constraints definiert
- So kann man testen, welche verschiedenen Darstellungen für das UI möglich sind.
- Beachte - diese Methode wird auf einer UIView aufgerufen!

```js
override func touchesBegan(_ touches: Set<UITouch>, with event: UIEvent?) {
	box.exerciseAmbiguityInLayout()
}
```

Jetzt springt es jedes mal an einen anderen Ort, wenn man auf die View klickt: 

![][image-1]

Man kann auch einfach abfragen, ob das Layout mehrdeutig ist oder nicht:

```js
print(vw.hasAmbiguousLayout)
```

Dieser Befehl gibt noch zusätzliche informationen aus:

![][image-2]

Beachte: Hier ist markiert, welcher Constraint ungenügend ist - das System weiss nicht, wo auf der X-Achse die View positioniert werden soll.

## Zusammenfassung
- Zweck dieser Methode
- Wie wird es angewendet (nicht den genauen Code kennen)

[image-1]:	assets/2023-04-05%2021.47.22.gif
[image-2]:	assets/Bildschirm%C2%ADfoto%202023-04-05%20um%2021.48.38.png

#learning unit#