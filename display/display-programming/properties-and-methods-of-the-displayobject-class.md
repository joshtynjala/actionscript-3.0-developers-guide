# Properties and methods of the DisplayObject class

All display objects are subclasses of the DisplayObject class, and as such they
inherit the properties and methods of the DisplayObject class. The properties
inherited are basic properties that apply to all display objects. For example,
each display object has an `x` property and a `y` property that specifies the
object's position in its display object container.

You cannot create a DisplayObject instance using the DisplayObject class
constructor. You must create another type of object (an object that is a
subclass of the DisplayObject class), such as a Sprite, to instantiate an object
with the `new` operator. Also, if you want to create a custom display object
class, you must create a subclass of one of the display object subclasses that
has a usable constructor function (such as the Shape class or the Sprite class).
For more information, see the
[DisplayObject](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/display/DisplayObject.html)
class description in the
[ActionScript 3.0 Reference for the Adobe Flash Platform](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/index.html).
