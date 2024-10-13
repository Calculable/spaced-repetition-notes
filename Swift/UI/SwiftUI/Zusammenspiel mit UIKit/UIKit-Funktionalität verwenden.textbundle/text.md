# UIKit-Funktionalität verwenden
🕸️

## Konzept-Zeichnung

### Neues Bild
![][image-1]

### Altes Bild
![][image-2]
(Typealias braucht es vermutlich nicht)

## Beispiel-Code Controller (nur verstehen)

```swift
struct EmojiPickerView: UIViewControllerRepresentable {
    
    @Binding var emoji: String
    
	//protokoll
    func makeUIViewController(context: Context) -> EmojiPickerViewController {
        let controller = EmojiPickerViewController()
        controller.delegate = context.coordinator
        return controller
    }
    
	//protokoll
    func updateUIViewController(_ uiViewController: EmojiPickerViewController, context: Context) {
		uiViewController.currentEmoji = emoji
	}
    
    typealias UIViewControllerType = EmojiPickerViewController

    func makeCoordinator() -> Coordinator {
      Coordinator(self)
    }
    
    class Coordinator: EmojiPickerDelegate {
        
        private let parent: EmojiPickerView

        init(_ parent: EmojiPickerView) {
          self.parent = parent
        }
        
        func didGetEmoji(emoji: String) {
            parent.emoji = emoji
        }
        
        
    }
}
```

## Beispiel-Code View

Man kann auch einfach `Views` statt `ViewControllers` verwenden:

```swift
Section("SwiftUI") {
    TextField("SwiftUI", text: $text)
}
Section("UIKit (mit did End Editing)") {
    UITextFieldWrapper(text: $text)
}

struct UITextFieldWrapper: UIViewRepresentable {
    @Binding var text: String
    
    func makeUIView(context: Context) -> UITextField {
        let textField = UITextField()
        textField.delegate = context.coordinator
        return textField
    }
    
    func updateUIView(_ uiView: UITextField, context: Context) {
        uiView.text = text
    }
    
    func makeCoordinator() -> Coordinator {
        Coordinator(self)
    }
    
    class Coordinator: NSObject, UITextFieldDelegate {
        var parent: UITextFieldWrapper
        
        init(_ textField: UITextFieldWrapper) {
            self.parent = textField
        }
        
        func textFieldDidEndEditing(_ textField: UITextField) {
            parent.text = textField.text ?? ""
        }
    }
}
```

![][image-3]

##  Ohne Delegate

Wenn man das Delegate nicht benötigt, kann man den Code deutlich kürzer machen:

```swift
import SwiftUI
import UIKit

struct UILabelWrapper: UIViewRepresentable {
    var text: String

    func makeUIView(context: Context) -> UILabel {
        let label = UILabel()
        label.textAlignment = .center
        return label
    }

    func updateUIView(_ uiView: UILabel, context: Context) {
        uiView.text = text
    }
}
```

## Zusammenfassung
(ohne Details) welche Komponenten spielen eine Rolle, wer hat welche Verantwortung, wie spielen sie zusammen?

[image-1]:	assets/UIViewControllerRepresentable.drawio.png
[image-2]:	assets/Konzeptzeichnung_UIKit.drawio.png
[image-3]:	assets/2023-07-28%2008.14.59.gif

#learning unit# #guide