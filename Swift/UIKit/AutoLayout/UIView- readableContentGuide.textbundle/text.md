#  UIView: readableContentGuide
📖

##  Konzept
- Das ist ein Property auf View, welches vom System zur verfügung gestellt wird.
- Das System sagt aus, welcher Bereich des Screens für "Lesbaren" Inhalt empfohlen ist
- Es passt sich automatisch an Split-Screen etc. an:

![][image-1]![][image-2]

##  Für Tabellen

Bei einer Table View kann man angeben, ob man möchte dass es sich daran hält: `cellLayoutMarginsFollowReadableWidth= true`


> Apple suggests to leave the default value unless you know that you will display a lot of text in the table.


![][image-3]![][image-4]

##  Quelle
[https://www.wwdcnotes.com/notes/wwdc18/235/][1]

##  Zusammenfassung
- Was ist das? (Konzept)



[1]:	https://www.wwdcnotes.com/notes/wwdc18/235/

[image-1]:	https://www.wwdcnotes.com/images/notes/wwdc18/235/ipad1.png
[image-2]:	https://www.wwdcnotes.com/images/notes/wwdc18/235/ipad2.png
[image-3]:	https://www.wwdcnotes.com/images/notes/wwdc18/235/table1.png
[image-4]:	https://www.wwdcnotes.com/images/notes/wwdc18/235/table2.png

#learning unit#