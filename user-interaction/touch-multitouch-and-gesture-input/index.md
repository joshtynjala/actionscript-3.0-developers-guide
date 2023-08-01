# Touch, multitouch and gesture input

<div>

<div>

The touch event handling features of the Flash Platform include input from a
single point of contact or multiple points of contact on touch-enabled devices.
And, the Flash runtimes handle events that combine multiple touch points with
movement to create a gesture. In other words, Flash runtimes interpret two types
of input:

Touch  
input with a single point device such as a finger, stylus, or other tool on a
touch-enabled device. Some devices support multiple simultaneous points of
contact with a finger or stylus.

Multitouch  
input with more than one simultaneous point of contact.

Gesture  
Input interpreted by a device or operating system in response to one or more
touch events. For example, a user rotates two fingers simultaneously, and the
device or operating system interprets that touch input as a rotation gesture.
Some gestures are performed with one finger or touch point, and some gestures
require multiple touch points. The device or operating system establishes the
type of gesture to assign to the input.

</div>

Both touch and gesture input can be multitouch input depending on the user's
device. ActionScript provides API for handling touch events, gesture events, and
individually tracked touch events for multitouch input.

<div>

Note: Listening for touch and gesture events can consume a significant amount of
processing resources (equivalent to rendering several frames per second),
depending on the computing device and operating system. It is often better to
use mouse events when you do not actually need the extra functionality provided
by touch or gestures. When you do use touch or gesture events, consider reducing
the amount of graphical changes that can occur, especially when such events can
be dispatched rapidly, as during a pan, rotate, or zoom operation. For example,
you could stop animation within a component while the user resizes it using a
zoom gesture.

</div>

- [Basics of touch input](WS1ca064e08d7aa93023c59dfc1257b16a3d6-8000.html)
- [Touch support discovery](WS7aa9c23539e7935d-52b3e55a1259fd2d9db-8000.html)
- [Touch event handling](WS1ca064e08d7aa93023c59dfc1257b16a3d6-7ffe.html)
- [Touch and drag](WS1ca064e08d7aa93023c59dfc1257b16a3d6-7ffc.html)
- [Gesture event handling](WS1ca064e08d7aa93023c59dfc1257b16a3d6-7ffd.html)
- [Troubleshooting](WS1ca064e08d7aa930-581fb7b1257b16ff45-8000.html)

</div>

<div>

<div>

More Help topics

</div>

<div>

</div>

![](images/flashplatformLinkIndicator.png)
[flash.ui.Multitouch](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/ui/Multitouch.html "https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/ui/Multitouch.html")

![](images/flashplatformLinkIndicator.png)
[flash.events.TouchEvent](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/TouchEvent.html "https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/TouchEvent.html")

![](images/flashplatformLinkIndicator.png)
[flash.events.GestureEvent](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/GestureEvent.html "https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/GestureEvent.html")

![](images/flashplatformLinkIndicator.png)
[flash.events.TransformGestureEvent](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/TransformGestureEvent.html "https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/TransformGestureEvent.html")

![](images/flashplatformLinkIndicator.png)
[flash.events.GesturePhase](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/GesturePhase.html "https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/GesturePhase.html")

![](images/flashplatformLinkIndicator.png)
[flash.events.PressAndTapGestureEvent](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/PressAndTapGestureEvent.html "https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/events/PressAndTapGestureEvent.html")

[Paul Trani: Touch Events and Gestures on Mobile](http://www.paultrani.com/blog/index.php/2011/02/touch-events-and-gestures-on-mobile/ "http://www.paultrani.com/blog/index.php/2011/02/touch-events-and-gestures-on-mobile/")

[Mike Jones: Virtual Game Controllers](http://blog.flashgen.com/2011/03/21/virtual-game-controllers/ "http://blog.flashgen.com/2011/03/21/virtual-game-controllers/")

<div>

</div>

</div>
