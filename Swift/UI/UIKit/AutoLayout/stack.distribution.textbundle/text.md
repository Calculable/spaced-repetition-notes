# stack.distribution
🥞

## Hinweise

In diesen Beispielen hat der Stack eine top, leading und bottom constraint um das Verhalten zu demonstrieren. Ohne diesen Constraint würde alles so aussehen:

![][image-1]

Rot ist die Farbe der Stackview (Hintergrund)

## fill (default)

> When the arranged views do not fit within the stack view, it shrinks the views according to their compression resistance priority. If the arranged views do not fill the stack view, it stretches the views according to their hugging priority.
![][image-2]


## fillEqually

> The views are resized so that they are all the same size along the stack view’s axis.
![][image-3]


## fillProportionally

> Views are resized proportionally based on their intrinsic content size along the stack view’s axis.
![][image-4]


## equalCentering

> the centers of the views are equally spaced along the stack view's axis. This means that the distance between the centers of adjacent views will be the same, but the actual spacing between their edges may vary, especially if the views have different sizes

![][image-5]


## equalSpacing
![][image-6]

##  Zusammenfassung
- Was ist der Default
- Wie verhalten sich: fill, fillEqually, fillProportionally, equalCentering, equalSpacing



[image-1]:	assets/simulator_screenshot_64BBD5F0-FB39-4819-94FA-B851A54B88B0.png
[image-2]:	assets/simulator_screenshot_62B9AD92-ADC3-45E2-8B18-C4BCF5036538.png
[image-3]:	assets/simulator_screenshot_0F75B458-FE4A-4C4F-A54D-4C1A4C7E782B.png
[image-4]:	assets/simulator_screenshot_6E51A057-1215-4EA2-AEE4-F2C2925C5A4B.png
[image-5]:	assets/simulator_screenshot_4368DFD8-E1F9-4B38-99DA-138F5A20340F.png
[image-6]:	assets/simulator_screenshot_B78112E1-19A6-4320-93E9-9F4C29508186.png

#learning unit# #guide