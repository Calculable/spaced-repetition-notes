# Picker
::4::

```swift
Picker("Select your student", selection: $selectedStudent){
	ForEach(students, id: \.self) {
		Text($0)
    }
}            
```

Wenn man nicht `ForEach` verwendet, dann braucht jeder Eintrag einen `tag`
![][image-1]

[image-1]:	assets/Bildschirmfoto%202022-07-20%20um%2018.08.24.png