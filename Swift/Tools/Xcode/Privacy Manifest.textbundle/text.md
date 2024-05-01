# Privacy Manifest
🥸
##  Zweck

- Damit kann man hinterlegen, welche Nutzerinformationen man sammelt
- Daraus kann man dann einen Report generieren, welcher auch die ganzen Dependencies berücksichtigt

> Your app’s privacy manifest file doesn’t need to cover data collected by third-party SDKs that your app links to.

> The privacy report is organized in a similar way to Privacy Nutrition Labels. Refer to this report when you provide your app’s privacy details in App Store Connect

## Privacy Manifest erstellen

-  Choose File \> New File.
- Scroll down to the Resource section, and select App Privacy File type.
- Click Next.
- Check your app or third-party SDK’s target in the Targets list.
- Click Create.
- By default, the file is named PrivacyInfo.xcprivacy; this is the required file name for bundled privacy manifests.

![][image-1]
![][image-2]

## Report generieren


> When you're building your app to submit to the App Store, Xcode 15 can aggregate all the privacy manifests in your app's project, and produce a privacy report that summarizes the declared data uses. 

![][image-3]![][image-4]


##  Siehe auch

[https://developer.apple.com/documentation/bundleresources/privacy\_manifest\_files/describing\_data\_use\_in\_privacy\_manifests][1]

[App privacy details on the App Store][2]

##  Zusammenfassung
- Was ist das?

[1]:	https://developer.apple.com/documentation/bundleresources/privacy_manifest_files/describing_data_use_in_privacy_manifests
[2]:	https://developer.apple.com/app-store/app-privacy-details/ "App privacy details on the App Store"

[image-1]:	assets/Bildschirmfoto%202024-03-19%20um%2017.01.20.png
[image-2]:	https://www.wwdcnotes.com/images/notes/wwdc23/10060/privacymanifest.png
[image-3]:	https://www.wwdcnotes.com/images/notes/wwdc23/10060/generateprivacyreport.png
[image-4]:	https://www.wwdcnotes.com/images/notes/wwdc23/10060/privacyreport.png

#learning unit#