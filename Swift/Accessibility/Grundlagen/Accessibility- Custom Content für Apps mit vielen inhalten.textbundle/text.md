# Accessibility: Custom Content für Apps mit vielen inhalten
🦮

## Zweck

Das sind zu viele Daten:
![][image-1]

Eigentlich möchte man es so:
![][image-2]

So kann man dann auf die weiteren Infos zugreifen mit dem Rotor:

![][image-3]

Jetzt kann man einfach nach unten oder oben Swipen um zu Adiditional Content zu springen

## Custom Content in den User-Einstellungen aktivieren

Voice Over -\> Verbosity -\> More Content

## UIKit

Accessibility Label enthält nur noch die minimalen Informationen:

Zusätzlich implementiert man dieses Protokoll:

![][image-4]
![][image-5]

Man kann auch importance auf High setzen. Dann wird es immer vorgelesen (nicht im More Content sondern automatisch nach dem accessibility Label)
![][image-6]
![][image-7]


## SwiftUI


```swift
import SwiftUI
import Accessibility

struct DogCell: View {
    var dog: Dog
    var body: some View {
        VStack {
            HStack {
                dog.image
                    .resizable()
                VStack(alignment: .leading) {
                    Text(dog.name)
                        .font(.title)
                    Spacer()
                    Text(dog.type)
                        .font(.body)
                    Spacer()
                    Text(dog.description)
                        .fixedSize(horizontal: false, vertical: true)
                        .font(.subheadline)
                        .foregroundColor(Color(uiColor: UIColor.brown)) //neu: foregroundStyle
                        .accessibilityHidden(true)
                }
                Spacer()
            }
            .padding(.horizontal)
            HStack(alignment: .top) {
                VStack(alignment: .leading) {
                    HStack {
                        Text(dog.popularity)
                        Spacer()
                        Text(dog.age)
                        Spacer()
                        Text(dog.weight)
                        Spacer()
                        Text(dog.height)
                    }
                    .foregroundColor(Color(uiColor: UIColor.darkGray)) //neu: foregroundStyle
                    .accessibilityHidden(true)
                }
                Spacer()
            }
            .padding(.horizontal)
            Divider()
        }
        .accessibilityElement(children: .combine)
        .accessibilityCustomContent("Age", dog.age, importance: .high)
        .accessibilityCustomContent("Popularity", dog.popularity)
        .accessibilityCustomContent("Weight", dog.weight)
        .accessibilityCustomContent("Height", dog.height)
        .accessibilityCustomContent("Description", dog.description)
    }
}
```

Wenn man keinen String Key haben möchte:

```swift
import SwiftUI
import Accessibility

extension AccessibilityCustomContentKey {
    static var age: AccessibilityCustomContentKey {
        AccessibilityCustomContentKey("Age")
    }
}

struct DogCell: View {
    var dog: Dog
    var body: some View {
        VStack {
            HStack {
                dog.image
                    .resizable()
                VStack(alignment: .leading) {
                    Text(dog.name)
                        .font(.title)
                    Spacer()
                    Text(dog.type)
                        .font(.body)
                    Spacer()
                    Text(dog.description)
                        .fixedSize(horizontal: false, vertical: true)
                        .font(.subheadline)
                        .foregroundColor(Color(uiColor: UIColor.brown)) //neu: foregroundStyle
                        .accessibilityHidden(true)
                }
                Spacer()
            }
            .padding(.horizontal)
            HStack(alignment: .top) {
                VStack(alignment: .leading) {
                    HStack {
                        Text(dog.popularity)
                        Spacer()
                        Text(dog.age)
                        Spacer()
                        Text(dog.weight)
                        Spacer()
                        Text(dog.height)
                    }
                    .foregroundColor(Color(uiColor: UIColor.darkGray)) //neu: foregroundStyle
                    .accessibilityHidden(true)
                }
                Spacer()
            }
            .padding(.horizontal)
            Divider()
        }
        .accessibilityElement(children: .combine)
        .accessibilityCustomContent(.age, dog.age, importance: .high)
        .accessibilityCustomContent("Popularity", dog.popularity)
        .accessibilityCustomContent("Weight", dog.weight)
        .accessibilityCustomContent("Height", dog.height)
        .accessibilityCustomContent("Description", dog.description)
    }
}
```

##  Quelle

Siehe: [https://a11y-guidelines.orange.com/en/mobile/ios/wwdc/2021/121/][1]

## Zusammenfassng
- Wie kann man also Voice Over User:in auf weitere Inhalte zugreifen, wenn diese zur Verfügung stehen?

[1]:	https://a11y-guidelines.orange.com/en/mobile/ios/wwdc/2021/121/

[image-1]:	assets/Bildschirmfoto%202024-02-03%20um%2012.50.54.png
[image-2]:	https://a11y-guidelines.orange.com/en/mobile/images/iOSdev/wwdc21-121-Using1.png
[image-3]:	assets/Bildschirmfoto%202024-02-03%20um%2012.52.24.png
[image-4]:	assets/Bildschirmfoto%202024-02-03%20um%2012.56.28.png
[image-5]:	assets/Bildschirmfoto%202024-02-03%20um%2012.55.42.png
[image-6]:	assets/Bildschirmfoto%202024-02-03%20um%2012.58.50.png
[image-7]:	assets/Bildschirmfoto%202024-02-03%20um%2012.59.04.png

#learning unit#