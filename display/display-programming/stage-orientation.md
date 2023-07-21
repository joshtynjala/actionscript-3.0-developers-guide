# Stage orientation

<div>

Mobile devices typically re-orient the user interface to keep the display
upright when the user rotates the device. If you enable auto-orientation in your
application, the device keeps the display properly oriented, but it is up to you
to make sure that your content looks okay when the aspect ratio of the stage
changes. If you disable auto-orientation, then the device display remains fixed
unless you change the orientation manually.

AIR applications run on a number of different mobile devices and operating
systems. The underlying orientation behavior can vary across operating systems,
and even across different devices on the same operating system. A simple design
strategy, that works well across all devices and operating systems, is to enable
auto-orientation and to listen for Stage `resize` events to determine when you
need to refresh the application layout.

Alternately, if your application only supports the portrait aspect ratio or only
supports the landscape aspect ratio, you can turn off auto-orientation and set
the supported aspect ratio in the AIR application descriptor. This design
strategy provides consistent behavior and selects the “best” orientation for the
selected aspect ratio. For example, if you specify the landscape aspect ratio,
the orientation chosen is appropriate for devices with landscape-mode, slide-out
keyboards.

</div>
