# Using the external API

The ActionScript 3.0 external API (
[flash.external.ExternalInterface](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/external/ExternalInterface.html))
enables straightforward communication between ActionScript and the container
application within which Adobe Flash Player is running. Use the
ExternalInterface API to create interaction between a SWF document and
JavaScript in an HTML page.

You can use the external API to interact with a container application, pass data
between ActionScript and JavaScript in an HTML page.

Some common external API tasks are:

- Getting information about the container application

- Using ActionScript to call code in a web page displayed in a browser or an AIR
  desktop application

- Calling ActionScript code from a web page

- Creating a proxy to simplify calling ActionScript code from a web page

Note: This discussion of the external interface only covers communication
between ActionScript in a SWF file and the container application that includes a
reference to the Flash Player or instance in which the SWF file is loaded. Any
other use of Flash Player within an application is outside the scope of this
documentation. Flash Player is designed to be used as a browser plug-in or as a
projector (standalone application). Other usage scenarios may have limited
support.

#### Using the external API in AIR

Since an AIR application does not have an external container, this external
interface does not generally apply—nor is it generally needed. When your AIR
application loads a SWF file directly, the application code can communicate
directly with the ActionScript code in the SWF (subject to security sandbox
restrictions).

However, when your AIR application loads a SWF file using an HTML page in an
HTMLLoader object (or an HTML component in Flex), the HTMLLoader object serves
as the external container. Thus, you can use the external interface to
communicate between the ActionScript code in the loaded SWF and the JavaScript
code in the HTML page loaded in the HTMLLoader.

- [Basics of using the external API](WS5b3ccc516d4fbf351e63e3d118a9b90204-7caa.html)
- [External API requirements and advantages](WS5b3ccc516d4fbf351e63e3d118a9b90204-7cab.html)
- [Using the ExternalInterface class](WS5b3ccc516d4fbf351e63e3d118a9b90204-7cb2.html)
- [External API example: Communicating between ActionScript and JavaScript in a web browser](WS5b3ccc516d4fbf351e63e3d118a9b90204-7cb1.html)
