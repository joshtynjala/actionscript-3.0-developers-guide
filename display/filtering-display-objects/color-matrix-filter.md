# Color matrix filter

<div>

The ColorMatrixFilter class is used to manipulate the color and alpha values of
the filtered object. This allows you to create saturation changes, hue rotation
(shifting a palette from one range of colors to another), luminance-to-alpha
changes, and other color manipulation effects using values from one color
channel and potentially applying them to other channels.

Conceptually, the filter goes through the pixels in the source image one by one
and separates each pixel into its red, green, blue, and alpha components. It
then multiplies values provided in the color matrix by each of these values,
adding the results together to determine the resulting color value that will be
displayed on the screen for that pixel. The `matrix` property of the filter is
an array of 20 numbers that are used in calculating the final color. For details
of the specific algorithm used to calculate the color values, see the entry
describing the ColorMatrixFilter class’s `matrix` property in the <a
href="http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/filters/ColorMatrixFilter.html"
target="_self">ActionScript 3.0 Reference for the Adobe Flash Platform</a>.

</div>
