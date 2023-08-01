# Monitoring NetStream activity

<div>

You can monitor NetStream activity to collect the information required to
support media usage analysis and reporting. The monitoring features discussed in
this section allow you to create media measurement libraries that collect data
without close coupling to the particular video player displaying the media. This
allows your client developers to choose their favorite video players when using
your library. Use the NetMonitor class to monitor the creation and activity of
NetStream objects in an application. The NetMonitor class provides a list of the
active NetStreams existing at any given time and also dispatches an event
whenever a NetStream object is created.

A NetStream object dispatches the events listed in the following table,
depending on the type of media being played:

<div>

| Event                             | Progressive download | RTMP streaming | HTTP streaming |
| --------------------------------- | -------------------- | -------------- | -------------- |
| NetStream.Play.Start              | Yes                  | Yes            | No             |
| NetStream.Play.Stop               | Yes                  | Yes            | No             |
| NetStream.Play.Complete           | Yes                  | Yes            | No             |
| NetStream.SeekStart.Notify        | Yes                  | Yes            | Yes            |
| NetStream.Seek.Notify             | Yes                  | Yes            | Yes            |
| NetStream.Unpause.Notify          | Yes                  | Yes            | Yes            |
| NetStream.Unpause.Notify          | Yes                  | Yes            | Yes            |
| NetStream.Play.Transition         | Not applicable       | Yes            | Not applicable |
| NetStream.Play.TransitionComplete | Not applicable       | Yes            | Not applicable |
| NetStream.Buffer.Full             | Yes                  | Yes            | Yes            |
| NetStream.Buffer.Flush            | Yes                  | Yes            | Yes            |
| NetStream.Buffer.Empty            | Yes                  | Yes            | Yes            |

</div>

The NetStreamInfo object associated with a NetStream instance also stores the
last metadata and XMP data objects that were encountered in the media.

When media is played via HTTP streaming, the NetStream.Play.Start,
NetStream.Play.Stop, and NetStream.Play.Complete are not dispatched since the
application has complete control of the media stream. A video player should
synthesize and dispatch these events for HTTP streams.

Likewise, NetStream.Play.Transition and NetStream.Play.TransitionComplete are
not dispatched for either progressive download or HTTP media. Dynamic bitrate
switching is an RTMP feature. If a video player using an HTTP stream supports a
similar feature, the player can synthesize and dispatch transition events.

</div>

<div>

<div>

More Help topics

</div>

<div>

[Monitoring NetStream events](WS901d38e593cd1bac-1201e73713000d1f624-8000.html)

[Detecting player domain](WS901d38e593cd1bac61bb910e130015e4804-8000.html)

</div>

[Adobe Developer Connection: Measuring video consumption in Flash](http://www.adobe.com/devnet/video/articles/media-measurement-flash.html)

<div>

</div>

</div>
