# Basics of copy-and-paste

<div>

The copy-and-paste API contains the following classes.

<div>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Package</p></th>
<th><p>Classes</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>flash.desktop</p></td>
<td><div>
<ul class="incremental">
<li><p><a
href="http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/desktop/Clipboard.html">Clipboard</a></p></li>
<li><p><a
href="http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/desktop/ClipboardFormats.html">ClipboardFormats</a></p></li>
<li><p><a
href="http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/desktop/ClipboardTransferMode.html">ClipboardTransferMode</a></p></li>
</ul>
</div></td>
</tr>
</tbody>
</table>

</div>

The static `Clipboard.generalClipboard` property represents the operating system
clipboard. The Clipboard class provides methods for reading and writing data to
clipboard objects.

The HTMLLoader class (in AIR) and the TextField class implement default behavior
for the normal copy and paste keyboard shortcuts. To implement copy and paste
shortcut behavior for custom components, you can listen for these keystrokes
directly. You can also use native menu commands along with key equivalents to
respond to the keystrokes indirectly.

Different representations of the same information can be made available in a
single Clipboard object to increase the ability of other applications to
understand and use the data. For example, an image might be included as image
data, a serialized Bitmap object, and as a file. Rendering of the data in a
format can be deferred so that the format is not actually created until the data
in that format is read.

</div>

<div>

<div>

</div>

</div>
