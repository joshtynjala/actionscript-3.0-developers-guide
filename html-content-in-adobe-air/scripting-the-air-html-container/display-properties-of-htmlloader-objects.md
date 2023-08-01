# Display properties of HTMLLoader objects

<div>

An HTMLLoader object inherits the display properties of the Adobe® Flash® Player
Sprite class. You can resize, move, hide, and change the background color, for
example. Or you can apply advanced effects like filters, masks, scaling, and
rotation. When applying effects, consider the impact on legibility. SWF and PDF
content loaded into an HTML page cannot be displayed when some effects are
applied.

HTML windows contain an HTMLLoader object that renders the HTML content. This
object is constrained within the area of the window, so changing the dimensions,
position, rotation, or scale factor does not always produce desirable results.

</div>

<div>

## Basic display properties

<div>

The basic display properties of the HTMLLoader allow you to position the control
within its parent display object, to set the size, and to show or hide the
control. You should not change these properties for the HTMLLoader object of an
HTML window.

The basic properties include:

<div>

| Property          | Notes                                                              |
| ----------------- | ------------------------------------------------------------------ |
| `x`, `y`          | Positions the object within its parent container.                  |
| `width`, `height` | Changes the dimensions of the display area.                        |
| `visible`         | Controls the visibility of the object and any content it contains. |

</div>

Outside an HTML window, the `width` and `height` properties of an HTMLLoader
object default to 0. You must set the width and height before the loaded HTML
content can be seen. HTML content is drawn to the HTMLLoader size, laid out
according to the HTML and CSS properties in the content. Changing the HTMLLoader
size reflows the content.

When loading content into a new HTMLLoader object (with `width` still set to 0),
it can be tempting to set the display `width` and `height` of the HTMLLoader
using the `contentWidth` and `contentHeight` properties. This technique works
for pages that have a reasonable minimum width when laid out according the HTML
and CSS flow rules. However, some pages flow into a long and narrow layout in
the absence of a reasonable width provided by the HTMLLoader.

<div>

Note: When you change the width and height of an HTMLLoader object, the scaleX
and scaleY values do not change, as would happen with most other types of
display objects.

</div>

</div>

</div>

<div>

## Transparency of HTMLLoader content

<div>

The `paintsDefaultBackground` property of an HTMLLoader object, which is `true`
by default, determines whether the HTMLLoader object draws an opaque background.
When `paintsDefaultBackground` is `false`, the background is clear. The display
object container or other display objects below the HTMLLoader object are
visible behind the foreground elements of the HTML content.

If the body element or any other element of the HTML document specifies a
background color (using `style="background-color:gray"`, for example), then the
background of that portion of the HTML is opaque and rendered with the specified
background color. If you set the `opaqueBackground` property of the HTMLLoader
object, and `paintsDefaultBackground` is `false`, then the color set for the
`opaqueBackground` is visible.

<div>

Note: You can use a transparent, PNG-format graphic to provide an alpha-blended
background for an element in an HTML document. Setting the opacity style of an
HTML element is not supported.

</div>

</div>

</div>

<div>

## Scaling HTMLLoader content

<div>

Avoid scaling an HTMLLoader object beyond a scale factor of 1.0. Text in
HTMLLoader content is rendered at a specific resolution and appears pixelated if
the HTMLLoader object is scaled up. To prevent the HTMLLoader, as well as its
contents, from scaling when a window is resized, set the `scaleMode` property of
the Stage to `StageScaleMode.NO_SCALE`.

</div>

</div>

<div>

## Considerations when loading SWF or PDF content in an HTML page

<div>

SWF and PDF content loaded into in an HTMLLoader object disappears in the
following conditions:

- If you scale the HTMLLoader object to a factor other that 1.0.

- If you set the alpha property of the HTMLLoader object to a value other than
  1.0.

- If you rotate the HTMLLoader content.

The content reappears if you remove the offending property setting and remove
the active filters.

In addition, the runtime cannot display PDF content in transparent windows. The
runtime only displays SWF content embedded in an HTML page when the `wmode`
parameter of the object or embed tag is set to `opaque` or `transparent`. Since
the default value of `wmode` is `window`, SWF content is not displayed in
transparent windows unless you explicitly set the wmode parameter.

<div>

Note: Prior to AIR 1.5.2, SWF embedded in HTML could not be displayed no matter
which wmode value was used.

</div>

For more information on loading these types of media in an HTMLLoader, see
[Embedding SWF content in HTML](WS4B441C24-BAE3-4110-91FD-A4E5EEFB2467.html) and
[Adding PDF content in AIR](WS5b3ccc516d4fbf351e63e3d118666ade46-7eb4.html).

</div>

</div>

<div>

## Advanced display properties

<div>

The HTMLLoader class inherits several methods that can be used for special
effects. In general, these effects have limitations when used with the
HTMLLoader display, but they can be useful for transitions or other temporary
effects. For example, if you display a dialog window to gather user input, you
could blur the display of the main window until the user closes the dialog.
Likewise, you could fade the display out when closing a window.

The advanced display properties include:

<div>

| Property           | Limitations                                                                                                                                                                                                         |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `alpha`            | Can reduce the legibility of HTML content                                                                                                                                                                           |
| `filters`          | In an HTML Window, exterior effects are clipped by the window edge                                                                                                                                                  |
| `graphics`         | Shapes drawn with graphics commands appear below HTML content, including the default background. The paintsDefaultBackground property must be false for the drawn shapes to be visible.                             |
| `opaqueBackground` | Does not change the color of the default background. The paintsDefaultBackground property must be false for this color layer to be visible.                                                                         |
| `rotation`         | The corners of the rectangular HTMLLoader area can be clipped by the window edge. SWF and PDF content loaded in the HTML content is not displayed.                                                                  |
| `scaleX`, `scaleY` | The rendered display can appear pixelated at scale factors greater than 1. SWF and PDF content loaded in the HTML content is not displayed.                                                                         |
| `transform`        | Can reduce legibility of HTML content. The HTML display can be clipped by the window edge. SWF and PDF content loaded in the HTML content is not displayed if the transform involves rotation, scaling, or skewing. |

</div>

The following example illustrates how to set the `filters` array to blur the
entire HTML display:

    var html:HTMLLoader = new HTMLLoader();
    var urlReq:URLRequest = new URLRequest("http://www.adobe.com/");
    html.load(urlReq);
    html.width = 800;
    html.height = 600;

    var blur:BlurFilter = new BlurFilter(8);
    var filters:Array = [blur];
    html.filters = filters;

</div>

</div>

<div>

<div>

</div>

</div>
