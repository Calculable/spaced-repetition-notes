# Accessibility: Label/Hint/Value Block Syntax
🦮 

## Hinweise
- Verfügbar seit iOS 17

##  Beispiel mit Accessibility Value


```swift
class ViewController: UIViewController {
    var isFiltered = false

    override func viewDidLoad() {
        super.viewDidLoad()
        // Set up views
        zoomView.accessibilityValueBlock = { [weak self] in
            guard let self else { return nil }
            return isFiltered ? "Filtered" : "Not Filtered"
        }
    }
}
```

=\> Wird jedes mal vom System aufgerufen, wenn das System den Block anfragt
(Mit iOS 17)


## Verfügbarkeit

Die Block-Syntax gibt es für sehr viele Accessibility Werte

```swift
// Basic accessibility
@available(iOS 17.0, *)
open var isAccessibilityElementBlock: AXBoolReturnBlock?

@available(iOS 17.0, *)
open var accessibilityLabelBlock: AXStringReturnBlock?

@available(iOS 17.0, *)
open var accessibilityValueBlock: AXStringReturnBlock?

@available(iOS 17.0, *)
open var accessibilityHintBlock: AXStringReturnBlock?

@available(iOS 17.0, *)
open var accessibilityTraitsBlock: AXTraitsReturnBlock?

@available(iOS 17.0, *)
open var accessibilityIdentifierBlock: AXStringReturnBlock?


// Defining accessibility text and language
@available(iOS 17.0, *)
open var accessibilityHeaderElementsBlock: AXArrayReturnBlock?

@available(iOS 17.0, *)
open var accessibilityAttributedLabelBlock: AXAttributedStringReturnBlock?

@available(iOS 17.0, *)
open var accessibilityAttributedHintBlock: AXAttributedStringReturnBlock?

@available(iOS 17.0, *)
open var accessibilityLanguageBlock: AXStringReturnBlock?

@available(iOS 17.0, *)
open var accessibilityTextualContextBlock: AXTextualContextReturnBlock?

@available(iOS 17.0, *)
open var accessibilityUserInputLabelsBlock: AXStringArrayReturnBlock?

@available(iOS 17.0, *)
open var accessibilityAttributedUserInputLabelsBlock: AXAttributedStringArrayReturnBlock?

@available(iOS 17.0, *)
open var accessibilityAttributedValueBlock: AXAttributedStringReturnBlock?


// Configuring behavior
@available(iOS 17.0, *)
open var accessibilityElementsHiddenBlock: AXBoolReturnBlock?

@available(iOS 17.0, *)
open var accessibilityRespondsToUserInteractionBlock: AXBoolReturnBlock?

@available(iOS 17.0, *)
open var accessibilityViewIsModalBlock: AXBoolReturnBlock?

@available(iOS 17.0, *)
open var accessibilityShouldGroupAccessibilityChildrenBlock: AXBoolReturnBlock?


// Navigating elements
@available(iOS 17.0, *)
open var accessibilityElementsBlock: AXArrayReturnBlock?

@available(iOS 17.0, *)
open var automationElementsBlock: AXArrayReturnBlock?

@available(iOS 17.0, *)
open var accessibilityContainerTypeBlock: AXContainerTypeReturnBlock?

@available(iOS 17.0, *)
open var accessibilityActivationPointBlock: AXPointReturnBlock?

@available(iOS 17.0, *)
open var accessibilityFrameBlock: AXRectReturnBlock?

@available(iOS 17.0, *)
open var accessibilityNavigationStyleBlock: AXNavigationStyleReturnBlock?

@available(iOS 17.0, *)
open var accessibilityPathBlock: AXPathReturnBlock?


// Actions
@available(iOS 17.0, *)
open var accessibilityActivateBlock: AXBoolReturnBlock?

@available(iOS 17.0, *)
open var accessibilityIncrementBlock: AXVoidReturnBlock?

@available(iOS 17.0, *)
open var accessibilityDecrementBlock: AXVoidReturnBlock?

@available(iOS 17.0, *)
open var accessibilityPerformEscapeBlock: AXBoolReturnBlock?

@available(iOS 17.0, *)
open var accessibilityMagicTapBlock: AXBoolReturnBlock?

@available(iOS 17.0, *)
open var accessibilityCustomActionsBlock: AXCustomActionsReturnBlock?
```

##  Zusammenfassung
- Konzept: Wozu ist das gut?

#learning unit#