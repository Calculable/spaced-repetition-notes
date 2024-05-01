# Required Reasons API
🥸
## Um was geht es?

- Ab 2024 muss man bei der Verwendung gewisser APIs deklarieren, für welchen Zweck man sie einsetzt
- Damit soll verhindert werden, dass man die APIs einsetzt,um user zu tracken.
- Ansonsten wird der App-Store-Connect-Build nicht angenommen
- Es gibt eine vordefinierte Liste mit Reasons. Die Reasons werden im Privacy Manifest eingetragen, siehe hier: [ulysses://x-callback-url/open?id=UvO-iccCeIETDCLU92W3PA][1]


## Beispiel

```swift
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
    <key>NSPrivacyTracking</key>
    <false/>
    <key>NSPrivacyCollectedDataTypes</key>
    <array/>
    <key>NSPrivacyTrackingDomains</key>
    <array/>
    <key>NSPrivacyAccessedAPITypes</key>
    <array>
        <dict>
            <key>NSPrivacyAccessedAPITypeReasons</key>
            <array>
                <string>35F9.1</string>
            </array>
            <key>NSPrivacyAccessedAPIType</key>
            <string>NSPrivacyAccessedAPICategorySystemBootTime</string>
        </dict>
        <dict>
            <key>NSPrivacyAccessedAPITypeReasons</key>
            <array>
                <string>C617.1</string>
            </array>
            <key>NSPrivacyAccessedAPIType</key>
            <string>NSPrivacyAccessedAPICategoryFileTimestamp</string>
        </dict>
        <dict>
            <key>NSPrivacyAccessedAPIType</key>
            <string>NSPrivacyAccessedAPICategoryDiskSpace</string>
            <key>NSPrivacyAccessedAPITypeReasons</key>
            <array>
                <string>85F4.1</string>
            </array>
        </dict>
        <dict>
            <key>NSPrivacyAccessedAPIType</key>
            <string>NSPrivacyAccessedAPICategoryUserDefaults</string>
            <key>NSPrivacyAccessedAPITypeReasons</key>
            <array>
                <string>CA92.1</string>
            </array>
        </dict>
    </array>
</dict>
</plist>

```

## Siehe auch
Privacy Manifests: [ulysses://x-callback-url/open?id=UvO-iccCeIETDCLU92W3PA][2]

## Quelle
[https://developer.apple.com/documentation/bundleresources/privacy\_manifest\_files#4284009][3]

##  Zusammenfassung
- Was ist das?



[1]:	ulysses://x-callback-url/open?id=UvO-iccCeIETDCLU92W3PA
[2]:	ulysses://x-callback-url/open?id=UvO-iccCeIETDCLU92W3PA
[3]:	https://developer.apple.com/documentation/bundleresources/privacy_manifest_files#4284009

#learning unit#