# Web service requests

<div>

There are a variety of HTTP-based web services. The main types include:

<div>

- REST

- XML-RPC

- SOAP

</div>

To use a web service in ActionScript 3, you create a URLRequest object,
construct the web service call using either URL variables or an XML document,
and send the call to the service using a URLLoader object. The Flex framework
contains several classes that make it easier to use web services—especially
useful when accessing complex SOAP services. Starting with Flash Professional
CS3, you can use the Flex classes in applications developed with Flash
Professional as well as in applications developed in Flash Builder.

In HTML-based AIR applications, you can use either the URLRequest and URLLoader
classes or the JavaScript XMLHttpRequest class. If desired, you can also create
a SWF library that exposes the web service components of the Flex framework to
your JavaScript code.

When your application runs in a browser, you can only use web services in the
same Internet domain as the calling SWF unless the server hosting the web
service also hosts a cross-domain policy file that permits access from other
domains. A technique that is often used when a cross-domain policy file is not
available is to proxy the requests through your own server. Adobe Blaze DS and
Adobe LiveCycle support web service proxying.

In AIR applications, a cross-domain policy file is not required when the web
service call originates from the application security sandbox. AIR application
content is never served from a remote domain, so it cannot participate in the
types of attacks that cross-domain policies prevent. In HTML-based AIR
applications, content in the application security sandbox can make cross-domain
XMLHttpRequests. You can allow content in other security sandboxes to make
cross-domain XMLHttpRequests as long as that content is loaded into an iframe.

</div>

<div>

<div>

More Help topics

</div>

<div>

[Website controls (policy files)](WS5b3ccc516d4fbf351e63e3d118a9b90204-7e08.html)

[REST-style web service requests](WSb2ba3b1aad8a27b061afd5d7127074bbf44-8000.html)

[XML-RPC web service requests](WSb2ba3b1aad8a27b061afd5d7127074bbf44-7fff.html)

[SOAP web service requests](WSb2ba3b1aad8a27b061afd5d7127074bbf44-7ffe.html)

</div>

![](images/flexLinkIndicator.png)
[Accessing server-side data](https://help.adobe.com/en_US/Flex/4.5/AccessingData/WS2db454920e96a9e51e63e3d11c0bf69084-7ff2.html "https://help.adobe.com/en_US/Flex/4.5/AccessingData/WS2db454920e96a9e51e63e3d11c0bf69084-7ff2.html")

[Adobe BlazeDS](http://opensource.adobe.com/wiki/display/blazeds/BlazeDS "http://opensource.adobe.com/wiki/display/blazeds/BlazeDS")

[Adobe LiveCycle ES2](http://www.adobe.com/devnet/livecycle/ "http://www.adobe.com/devnet/livecycle/")

[REST architecture](http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm "http://www.ics.uci.edu/~fielding/pubs/dissertation/rest_arch_style.htm")

[XML-RPC](http://en.wikipedia.org/wiki/XML-RPC "http://en.wikipedia.org/wiki/XML-RPC")

[SOAP protocol](http://www.w3.org/TR/soap/ "http://www.w3.org/TR/soap/")

<div>

</div>

</div>