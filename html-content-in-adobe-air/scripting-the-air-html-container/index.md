# Scripting the AIR HTML Container

The
[HTMLLoader](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/html/HTMLLoader.html)
class serves as the container for HTML content in Adobe® AIR®. The class
provides many properties and methods, inherited from the Sprite class, for
controlling the behavior and appearance of the object on the ActionScript® 3.0
display list. In addition, the class defines properties and methods for such
tasks as loading and interacting with HTML content and managing history.

The
[HTMLHost](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/html/HTMLHost.html)
class defines a set of default behaviors for an HTMLLoader. When you create an
HTMLLoader object, no HTMLHost implementation is provided. Thus when HTML
content triggers one of the default behaviors, such as changing the window
location, or the window title, nothing happens. You can extend the HTMLHost
class to define the behaviors desired for your application.

A default implementation of the HTMLHost is provided for HTML windows created by
AIR. You can assign the default HTMLHost implementation to another HTMLLoader
object by setting the `htmlHost` property of the object using a new HTMLHost
object created with the `defaultBehavior` parameter set to `true`.

Note: In the Adobe® Flex™ Framework, the HTMLLoader object is wrapped by the
mx:HTML component. When using Flex, use the HTML component.

- [Display properties of HTMLLoader objects](WS5b3ccc516d4fbf351e63e3d118666ade46-7e79.html)
- [Scrolling HTML content](WS5b3ccc516d4fbf351e63e3d118666ade46-7e65.html)
- [Accessing the HTML history list](WS5b3ccc516d4fbf351e63e3d118666ade46-7e78.html)
- [Setting the user agent used when loading HTML content](WS5b3ccc516d4fbf351e63e3d118666ade46-7e7b.html)
- [Setting the character encoding to use for HTML content](WS5b3ccc516d4fbf351e63e3d118666ade46-7e7a.html)
- [Defining browser-like user interfaces for HTML content](WS5b3ccc516d4fbf351e63e3d118666ade46-7e74.html)
- [Creating subclasses of the HTMLLoader class](WS5b3ccc516d4fbf351e63e3d118666ade46-7e64.html)
