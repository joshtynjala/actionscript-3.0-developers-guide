# Using digital rights management

Adobe® Access™ is a content protection solution. It lets content owners,
distributors, and advertisers realize new sources of revenue by providing
seamless access to premium content. Publishers use Adobe Access to encrypt
content, create policies, and issue licenses. Adobe Flash Player and Adobe AIR
incorporate a DRM library, the Adobe Access module. This module enables the
runtime to communicate with the Adobe Access license server and play back
protected content. The runtime thus completes the life cycle of content
protected by Adobe Access and distributed by Flash Media Server.

With Adobe Access, content providers can provide both free content and premium
content. For example, a consumer wants to view a television program without
advertisements. The consumer registers and pays the content publisher. The
consumer can then enter their user credentials to gain access and play the
program without the ads.

In another example, a consumer wants to view content offline while traveling
with no Internet access. This offline workflow is supported in AIR applications.
After registering and paying the publisher for the content, the user can access
and download the content and associated AIR application from the publisher's
website. Using the AIR application, the user can view the content offline during
the permitted period. The content can also be shared with other devices in the
same device group using domains ( **New in 3.0** ).

Adobe Access also supports anonymous access, which does not require user
authentication. For example, a publisher can use anonymous access to distribute
ad-supported content. Anonymous access also lets a publisher allow free access
to the current content for a specified number of days. The content provider can
also specify and restrict the type and version of the player needed for their
content.

When a user tries to play protected content in Flash Player or Adobe AIR, your
application must call the DRM APIs. The DRM APIs initiate the workflow for
playback of protected content. The runtime, through the Adobe Access module,
contacts the license server. The license server authenticates the user, if
necessary, and issues a license to allow playback of protected content. The
runtime receives the license and decrypts the content for playback.

How to enable your application to play content protected by Adobe Access is
described here. It is not necessary to understand how to encrypt content or
maintain policies using Adobe Access. However, it is assumed that you are
communicating with the Adobe Access license server to authenticate the user and
retrieve the license. It is also assumed that you are designing an application
to specifically play content protected by Adobe Access.

For an overview of Adobe Access, including creating policies, see the
documentation included with Adobe Access.

- [Understanding the protected content workflow](WS5b3ccc516d4fbf351e63e3d118666ade46-7ce3.html)
- [DRM-related members and events of the NetStream class](WS5b3ccc516d4fbf351e63e3d118666ade46-7cdb.html)
- [Using the DRMStatusEvent class](WS5b3ccc516d4fbf351e63e3d118666ade46-7cda.html)
- [Using the DRMAuthenticateEvent class](WS5b3ccc516d4fbf351e63e3d118666ade46-7cd9.html)
- [Using the DRMErrorEvent class](WS5b3ccc516d4fbf351e63e3d118666ade46-7cd8.html)
- [Using the DRMManager class](WSe3d2d52902616553-41317b6911d1b4bfb29-8000.html)
- [Using the DRMContentData class](WSe3d2d52902616553-41317b6911d1b4bfb29-7ffb.html)
- [Updating Flash Player to support Adobe Access](WS7568cbd5c81a0ea6-4ef57b4b126d9b14f0e-8000.html)
- [Out-of-band Licenses](WS5262178513756206-78d23af81315fed2b54-8000.html)
- [Domain support](WS5262178513756206-ae26abd131600c5818-8000.html)
- [Playing encrypted content using domain support](WS5262178513756206-78d23af81315fed2b54-7fff.html)
- [License preview](WS526217851375620669910b54131a93d5a97-8000.html)
- [Delivering content](WS52621785137562065c5bbf86131a9559a30-8000.html)
- [Open Source Media Framework](WS5262178513756206-afd4008131d686aef7-8000.html)

More Help topics

![](../../img/flashplatformLinkIndicator.png)
[flash.net.drm package](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/drm/package-detail.html)

![](../../img/flashplatformLinkIndicator.png)
[flash.net.NetConnection](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/NetConnection.html)

![](../../img/flashplatformLinkIndicator.png)
[flash.net.NetStream](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/net/NetStream.html)
