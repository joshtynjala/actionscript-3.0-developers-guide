# Basics of video

One important capability of Adobe® Flash® Player and Adobe® AIR™ is the ability
to display and manipulate video information with ActionScript in the same way
that you can manipulate other visual content such as images, animation, text,
and so on. When you create a Flash Video (FLV) file in Adobe Flash CS4
Professional, you have the option to select a skin that includes common playback
controls. However, there is no reason you need to limit yourself to the options
available. Using ActionScript, you have fine-tuned control over loading,
displaying, and playback of video—meaning you could create your own video player
skin, or use your video in any less traditional way that you want. Working with
video in ActionScript involves working with a combination of several classes:

- <a
  href="https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/media/Video.html"
  target="_self">Video class</a>: The classic video content box on the Stage is
  an instance of the Video class. The Video class is a display object, so it can
  be manipulated using the same techniques that can be applied to other display
  objects, such as positioning, applying transformations, applying filters and
  blending modes, and so forth.

- <a
  href="http://help.stage.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/media/StageVideo.html"
  target="_self">StageVideo class</a>: The Video class typically uses software
  decoding and rendering. When GPU hardware acceleration is available on a
  device, your application can take best advantage of hardware accelerated
  presentation by switching to the StageVideo class. The StageVideo API includes
  a set of events that tell your code when to switch between StageVideo and
  Video objects. Stage video imposes some minor restrictions on video playback.
  If your application accepts those limitations, implement the StageVideo API.
  See
  [Guidelines and limitations](WSe9ecd9e6b89aefd2-70150d4b12ccd2cd415-7ffe.html).

- <a
  href="https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/NetStream.html"
  target="_self">NetStream class</a>: When you're loading a video file to be
  controlled by ActionScript, a NetStream instance represents the source of the
  video content—in this case, a stream of video data. Using a NetStream instance
  also involves using a NetConnection object, which is the connection to the
  video file—like the tunnel that the video data is fed through.

- <a
  href="https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/media/Camera.html"
  target="_self">Camera class</a>: When you're working with video data from a
  camera connected to the user's computer, a Camera instance represents the
  source of the video content—the user's camera and the video data it makes
  available. New in Flash Player 11.4 and AIR 3.4, you can use a camera to feed
  StageVideo.

When you're loading external video, you can load the file from a standard web
server for progressive download, or you can work with streaming video delivered
by a specialized server such as Adobe's Flash® Media Server.

#### Important concepts and terms

Cue point  
A marker that can be placed at a specific moment in time in a video file, for
example to act like a bookmark for locating that point in time, or to provide
additional data that is associated with that moment in time.

Encoding  
The process of taking video data in one format and converting it to another
video data format; for example, taking a high-resolution source video and
converting it to a format that's suitable for Internet delivery.

Frame  
A single segment of video information; each frame is like a still image
representing a snapshot of a moment in time. By playing frames in sequence at
high speed, the illusion of motion is created.

Keyframe  
A video frame which contains the full information for the frame. Other frames
that follow a keyframe only contain information about how they differ from the
keyframe, rather than containing the full frame's worth of information.

Metadata  
Information about a video file that is embedded within the video file and
retrieved when the video has loaded.

Progressive download  
When a video file is delivered from a standard web server, the video data is
loaded using progressive download, meaning the video information loads in
sequence. This has the benefit that the video can begin playing before the
entire file is downloaded; however, it prevents you from jumping ahead to a part
of the video that hasn't loaded.

Streaming  
As an alternative to progressive download, a special video server can be used to
deliver video over the Internet using a technique known as streaming (sometimes
called "true streaming"). With streaming, the viewer's computer never downloads
the entire video at one time. To speed up download times, at any moment the
computer only needs a portion of the total video information. Because a special
server controls the delivery of the video content, any part of the video can be
accessed at any time, rather than needing to wait for it to download before
accessing it.
