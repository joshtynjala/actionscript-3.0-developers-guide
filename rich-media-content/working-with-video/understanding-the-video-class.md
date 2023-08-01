# Understanding the Video class

The Video class enables you to display live streaming video in an application
without embedding it in your SWF file. You can capture and play live video using
the `Camera.getCamera()` method. You can also use the Video class to play back
video files over HTTP or from the local file system. There are several different
ways to use Video in your projects:

- Load a video file dynamically using the NetConnection and NetStream classes
  and display the video in a Video object.

- Capture input from the user's camera. For more information, see
  [Working with cameras](WSfffb011ac560372f3fa68e8912e3ab6b8cb-8000.html).

- Use the FLVPlayback component.

- Use the VideoDisplay control.

Note: Instances of a Video object on the Stage are instances of the Video class.

Even though the Video class is in the flash.media package, it inherits from the
flash.display.DisplayObject class. Therefore, all display object functionality,
such as matrix transformations and filters, also applies to Video instances.

For more information see
[Manipulating display objects](WS5b3ccc516d4fbf351e63e3d118a9b90204-7e0c.html),
[Working with geometry](WS5b3ccc516d4fbf351e63e3d118a9b90204-7e23.html), and
[Filtering display objects](WS5b3ccc516d4fbf351e63e3d118a9b90204-7e37.html).
