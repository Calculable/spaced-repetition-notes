# UIKit-Funktionalität verwenden
🕸️

## Konzept-Zeichnung

![][image-1]

## Beispiel-Code (nur verstehen)

```swift
struct EmojiPickerView: UIViewControllerRepresentable {
    
    @Binding var emoji: String
    
    func makeUIViewController(context: Context) -> EmojiPickerViewController {
        let controller = EmojiPickerViewController()
        controller.delegate = context.coordinator
        return controller
    }
    
    func updateUIViewController(_ uiViewController: EmojiPickerViewController, context: Context) {}
    
    
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

## Zusammenfassung
(ohne Details) welche Komponenten spielen eine Rolle, wer hat welche Verantwortung, wie spielen sie zusammen?

[image-1]:	assets/Konzeptzeichnung_UIKit.drawio.png