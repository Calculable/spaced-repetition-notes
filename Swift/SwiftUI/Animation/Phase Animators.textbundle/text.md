# Phase Animators
🐇

##  Grundlagen
- Phasen können beliebige Sequenzen sein
- Am einfachsten mit `CaseIterable` enum


```swift
Text("Test")
    .font(.largeTitle)
    .phaseAnimator([0, 1, 5]) { proxy, phase in
        proxy
            .scaleEffect(phase)
    }
```

Beachte: Es beginnt automatisch von vorne zu laufen:

![][image-1]
(Mit einem Trigger kann man verhindern, dass es für immer läuft)

## Trigger

```swift
.phaseAnimator(AnimationPhase.allCases, trigger: animationStep)
```

Der Trigger kann ein beliebiger Typ sein. Wenn er sich ändert, wird die Animation einmal durchgespielt und dann wieder abgestellt

## Phase Animator View:

```swift
PhaseAnimator([0, 1, 5]) { value in
    Text("Test")
        .font(.largeTitle)
        .scaleEffect(value)
    Text("Test 2")
        .font(.largeTitle)
        .rotationEffect(Angle(degrees: value * 30))
}
```

Damit kann man mehrere Views unabängig animieren

![][image-2]

##  Best Practice: Ein Enum für die Phasen verwenden:

```swift
enum MyCustomAnimationPhases: CaseIterable {
    case fadingIn, middle, zoomingOut

    var scale: Double {
        switch self {
	        case .zoomIn: 0
	        case .wait: 1
	        case .zoomOut: 5
        }
    }
}
```


```swift
.phaseAnimator(MyCustomAnimationPhases.allCases) { content, phase in
	content
		.scaleEffect(phase.scale)
}
```

Mann kann sogar für jede Phase einen eigenen Animationstyp definieren:

```swift
.phaseAnimator(AnimationPhase.allCases, trigger: animationStep) { 
	//.... animation
} animation: { phase in
    switch phase {
        case .zoomIn, .wait: .easeIn
        case .zoomOut: .easeOut(duration: 4)
    }
}
```

## Unterschied zu Keyframe Animation

- Im Gegensatz zu Keyframe Animations laufen die Animationen nacheinander und nicht paralell

## Zusammenfassung
- Grundlagen: Animation mit verschiedenen Phasen (nur ersten Abschnitt, ohne Trigger, Enum Best Practice, Phase Animator View…)

[image-1]:	assets/2023-06-17%2020.06.22.gif
[image-2]:	assets/2023-06-17%2020.09.51.gif

#learning unit# #iOS17