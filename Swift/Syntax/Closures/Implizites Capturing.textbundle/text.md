# Implizites Capturing
🦋

##  Verhalten
- Closures in Swift haben implizit / per default **starke Referenzen** auf die verwendeten Objekte. In einigen Fällen ist das ok, in anderen Fällen muss man aufpassen dass man keinen Retain Cycle bekommt, wobei sich zwei objekte gegenseitig stark referenzieren.

=\> Man muss aber jeweils `.self` schreiben, um es offensichtlicher zu machen dass gerade ein Capturing stattfindet

## Zusammenfassung
- Wie ist das implizite Capturing-Verhalten von Swift Closures?

#learning unit#