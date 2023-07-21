# Asynchronous decoding of bitmap images

<div>

When you work with bitmap images, you can asynchronously decode and load the
bitmap images to improve your application’s perceived performance. Decoding a
bitmap image asynchronously can take the same time as decoding the image
synchronously in many cases. However, the bitmap image gets decoded in a
separate thread before the associated `Loader` object sends the `COMPLETE`
event. Hence, you can asynchronously decode larger images after loading them.

The `ImageDecodingPolicy` class in the `flash.system` package, allows you to
specify the bitmap loading scheme. The default loading scheme is synchronous.

<div>

<table data-border="1" data-cellpadding="4" data-cellspacing="0">
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead data-align="left">
<tr class="header">
<th data-valign="top" width="NaN%"><p>Bitmap Decoding Policy</p></th>
<th data-valign="top" width="NaN%"><p>Bitmap Loading Scheme</p></th>
<th data-valign="top" width="NaN%"><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td headers="d17e20992 " data-valign="top"
width="NaN%"><p><samp>                                         ImageDecodingPolicy.ON_DEMAND                                     </samp></p></td>
<td headers="d17e20995 " data-valign="top"
width="NaN%"><p>Synchronous</p></td>
<td headers="d17e20998 " data-valign="top" width="NaN%"><p>Loaded images
are decoded when the image data is accessed.</p>
<p>Use this policy to decode smaller images. You can also use this
policy when your application does not rely on complex effects and
transitions.</p></td>
</tr>
<tr class="even">
<td headers="d17e20992 " data-valign="top"
width="NaN%"><p><samp>                                         ImageDecodingPolicy.ON_LOAD                                     </samp></p></td>
<td headers="d17e20995 " data-valign="top"
width="NaN%"><p>Asynchronous</p></td>
<td headers="d17e20998 " data-valign="top" width="NaN%"><p>Loaded images
are decoded on load, before the
<samp>COMPLETE</samp>
event is dispatched.</p>
<p>Ideal for larger images (greater than 10 MP). When you are developing
AIR-based mobile applications with page transitions, use this bitmap
loading policy to improve your application’s perceived
performance.</p></td>
</tr>
</tbody>
</table>

</div>

<div>

Note: If the file being loaded is a bitmap image and the decoding policy used is
`ON_LOAD`, the image is decoded asynchronously before the `COMPLETE` event is
dispatched.

</div>

The following code shows the usage of the `ImageDecodingPolicy` class:

    var loaderContext:LoaderContext = new LoaderContext();
    loaderContext.imageDecodingPolicy = ImageDecodingPolicy.ON_LOAD
    var loader:Loader = new Loader();
    loader.load(new URLRequest("http://www.adobe.com/myimage.png"), loaderContext);

You can still use `ON_DEMAND` decoding with `Loader.load()` and
`Loader.loadBytes()` methods. However, all the other methods that take a
`LoaderContext` object as an argument, ignore any `ImageDecodingPolicy` value
passed.

The following example shows the difference in decoding a bitmap image
synchronously and asynchronously:

    package
    {
    import flash.display.Loader;
    import flash.display.Sprite;
    import flash.events.Event;
    import flash.net.URLRequest;
    import flash.system.ImageDecodingPolicy;
    import flash.system.LoaderContext;

    public class AsyncTest extends Sprite
    {
        private var loaderContext:LoaderContext;
        private var loader:Loader;
        private var urlRequest:URLRequest;
        public function AsyncTest()
        {
            //Load the image synchronously
            loaderContext = new LoaderContext();
            //Default behavior.
            loaderContext.imageDecodingPolicy = ImageDecodingPolicy.ON_DEMAND;
            loader = new Loader();
            loadImageSync();

            //Load the image asynchronously
            loaderContext = new LoaderContext();
            loaderContext.imageDecodingPolicy = ImageDecodingPolicy.ON_LOAD;
            loader = new Loader();
            loadImageASync();
        }

        private function loadImageASync():void{
            trace("Loading image asynchronously...");
            urlRequest = new URLRequest("http://www.adobe.com/myimage.png");
            urlRequest.useCache = false;
            loader.load(urlRequest, loaderContext);
            loader.contentLoaderInfo.addEventListener
                (Event.COMPLETE, onAsyncLoadComplete);
        }

        private function onAsyncLoadComplete(event:Event):void{
            trace("Async. Image Load Complete");
        }

        private function loadImageSync():void{
            trace("Loading image synchronously...");
            urlRequest = new URLRequest("http://www.adobe.com/myimage.png");
            urlRequest.useCache = false;
            loader.load(urlRequest, loaderContext);
            loader.contentLoaderInfo.addEventListener
                (Event.COMPLETE, onSyncLoadComplete);
        }

        private function onSyncLoadComplete(event:Event):void{
            trace("Sync. Image Load Complete");
        }
    }
    }

For a demonstration of the effect of the different decoding policies, see
<a href="http://www.bytearray.org/?p=2931" target="_self">Thibaud Imbert:
Asynchronous bitmap decoding in the Adobe Flash runtimes</a>

</div>
