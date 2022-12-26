# UIKit-Funktionalität verwenden
::31::

## Konzept-Zeichnung

![][image-1]

## Beispiel-Code (nur verstehen)

```swift
import SwiftUI
import PhotosUI

struct PhotoPicker: UIViewControllerRepresentable {
  typealias UIViewControllerType = PHPickerViewController

  let filter: PHPickerFilter
  var limit: Int = 0 // 0 == 'no limit'.
  let onComplete: ([PHPickerResult]) -> Void

  func makeUIViewController(context: Context) -> PHPickerViewController {
    var configuration = PHPickerConfiguration()
    configuration.filter = filter
    configuration.selectionLimit = limit
    let controller = PHPickerViewController(configuration: configuration)
    controller.delegate = context.coordinator
    return controller
  }

  func updateUIViewController(_ uiViewController: PHPickerViewController, context: Context) {}

  func makeCoordinator() -> Coordinator { //diese Methode wird automatisch von SwiftUI aufgerufen.!!!
    Coordinator(self)
  }

  class Coordinator: PHPickerViewControllerDelegate {

    func picker(_ picker: PHPickerViewController, didFinishPicking results: [PHPickerResult]) {
      parent.onComplete(results)
      picker.dismiss(animated: true)
    }

    private let parent: PhotoPicker

    init(_ parent: PhotoPicker) {
      self.parent = parent
    }
  }

  static func convertToUIImageArray(fromResults results: [PHPickerResult], onComplete: @escaping ([UIImage]?, Error?) -> Void) {
    var images = [UIImage]()

    let dispatchGroup = DispatchGroup()

    for result in results {
      dispatchGroup.enter()
      let itemProvider = result.itemProvider
      if itemProvider.canLoadObject(ofClass: UIImage.self) {
        itemProvider.loadObject(ofClass: UIImage.self) { (imageOrNil, errorOrNil) in
          if let error = errorOrNil {
            onComplete(nil, error)
            dispatchGroup.leave()
          }
          if let image = imageOrNil as? UIImage {
            images.append(image)
            dispatchGroup.leave()
          }
        }
      }
    }
    dispatchGroup.notify(queue: .main) {
      onComplete(images, nil)
    }
  }
}
```

[image-1]:	assets/Konzeptzeichnung_UIKit.drawio.png