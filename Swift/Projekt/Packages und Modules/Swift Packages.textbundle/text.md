# Swift Packages

## Informationen
[https://developer.apple.com/documentation/swift\_packages][1]

![][image-1]


##  Package und App Tandem
- Man kann auch ein Swift Package in Tandem mit einer App erstellen: [ArticleDeveloping a Swift Package in Tandem with an App][2]


## Was ist ein Package?
- Wiederverwendbare Codeteile (Swift, Objective-C, C oder C\+\+)

##  Package veröffentlichen

> A package author can publish their Swift package to either public or private repositories. Xcode supports both private and publicly available packages.

## Package-Dependencies zu, Projekt hinzufügen

In Xcode: `File > Swift Packages > Add Package Dependency` and enter its repository URL. 

Alternativ: In den Projekteinstellungen unter „Frameworks, „Libraries und Embedded Content“

Anschliessend kann man es importieren:

```swift
import MyLibrary
```

::Hinweis: Package.resolved soll gepusht werden, damit alle mit der gleichen Version arbeiten ::

## Eingebundene Dependencies aktualisieren

> Although Xcode updates your package dependencies and resolves package versions automatically, you can trigger both actions from the File \> Swift Packages menu.

##  Wie kann man die Dependencies verändern?

> You can’t edit the content of your package dependencies directly. If you want to make changes to a package dependency, you need to add it as a local package to your project. See Editing a Package Dependency as a Local Package 

## Source-Based Packages vs. Binary Packages

- Binary Packages schützt intelectual properties des Authors besser, aber als Anwender kann man es nicht so gut debuggen.
- Binary Packages sind nur für Apple Plattformen verfügbar.


##  Eigenes Package erstellen

- Entweder als Executable Code (Script) als Executable Product oder als Library Product
- To create a new Swift package, open Xcode and select `File > New > Swift Package`
- wift packages don’t use .xcproject or .xcworkspace

So sieht die Struktur aus:

![][image-2]

### Package.swift

- „Package Manifest“
- Beispiel:

```swift
// swift-tools-version:5.3
import PackageDescription

let package = Package(
    name: "MyLibrary",
    platforms: [
        .macOS(.v10_14), .iOS(.v13), .tvOS(.v13)
    ],
    products: [
        // Products define the executables and libraries a package produces, and make them visible to other packages.
        .library(
            name: "MyLibrary",
            targets: ["MyLibrary", "SomeRemoteBinaryPackage", "SomeLocalBinaryPackage"])
    ],
    dependencies: [
        // Dependencies declare other packages that this package depends on.
  		.package(url: "https://url/of/another/package.git", from: "1.0.0"),
    	.package(path: "path/to/a/local/package/", "1.0.0"..<"2.0.0")
    ],
    targets: [
        // Targets are the basic building blocks of a package. A target can define a module or a test suite.
        // Targets can depend on other targets in this package, and on products in packages this package depends on.
        .target(
            name: "MyLibrary",
            exclude: ["instructions.md"],
            resources: [
                .process("text.txt"),
                .process("example.png"),
                .copy("settings.plist")
            ]
        ),
        .binaryTarget(
            name: "SomeRemoteBinaryPackage",
            url: "https://url/to/some/remote/binary/package.zip",
            checksum: "The checksum of the XCFramework inside the ZIP archive."
        ),
        .binaryTarget(
            name: "SomeLocalBinaryPackage",
            path: "path/to/some.xcframework"
        )
        .testTarget(
            name: "MyLibraryTests",
            dependencies: ["MyLibrary"]),
    ]
)
```

Convention: The package manifest above declares the MyLibrary target. Its source files reside in Sources/MyLibrary while source files for tests reside in Sources/MyLibraryTests

See Package.Dependency for all possible ways to declare a package dependency. 


## Organizing your Code with Local Packages

> As you develop your app, organize its code in a modular way to keep it maintainable by creating Swift packages and using them as local packages.

Man erstellt Packages und fügt sie dann hinzu.

> When you organize your app’s codebase using local packages, your Swift package’s code is part of the same repository as your app’s code. As you create more apps, consider moving local packages to their own Git repositories, and add them to your apps as a package dependency to reuse code across apps.

Siehe: [https://developer.apple.com/documentation/swift\_packages/organizing\_your\_code\_with\_local\_packages][3]

## Konvertierung von Geotaggy von einem Xcode-Projekt in ein Swift Package?

Ich habe ein neues Package angelegt und die Source reinkopiert.

- Im Package.swift mussten noch die Dependencies hinzugefügt werden.
- Zudem habe ich als „Product“ ein `executable` statt einer Library genommen

[1]:	https://developer.apple.com/documentation/swift_packages
[2]:	https://developer.apple.com/documentation/swift_packages/developing_a_swift_package_in_tandem_with_an_app "ArticleDeveloping a Swift Package in Tandem with an App"
[3]:	https://developer.apple.com/documentation/swift_packages/organizing_your_code_with_local_packages

[image-1]:	assets/DraggedImage.png
[image-2]:	assets/Bildschirmfoto%202021-06-02%20um%2018.45.59.png

#guide