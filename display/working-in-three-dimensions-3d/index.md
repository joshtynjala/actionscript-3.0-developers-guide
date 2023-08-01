# Working in three dimensions (3D)

<div>

The Flash Player and AIR runtimes support 3D graphics in two ways. You can use
three-dimensional display objects on the Flash display list. This is appropriate
for adding three-dimensional effects to Flash content and for low polygon-count
objects. In Flash Player 11and AIR 3, or later, you can render complex 3D scenes
using the Stage3D API.

A Stage3D viewport is not a display object. Instead, the 3D graphics are
rendered to a viewport that is displayed underneath the Flash display list (and
above any StageVideo viewport planes). Rather than using the Flash DisplayObject
classes to create a scene, you use a programmable 3D-pipeline (similar to OpenGL
and Direct3D). This pipeline takes triangle data and textures as input and
renders the scene using shader programs that you provide. Hardware acceleration
is used when a compatible graphics processing unit (GPU) with supported drivers,
is available on the client computer.

<a
href="https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/display/Stage3D.html"
target="_self">Stage3D</a> provides a very low-level API. In an application, you
are encouraged to use a 3D framework that supports Stage3D. You can create your
own framework or use one of several commercial and open source frameworks
already available.

For more information about developing 3D applications using Stage3D and about
available 3D frameworks, visit the
<a href="http://goo.gl/hlzhB" target="_self">Flash Player Developer Center:
Stage 3D</a>.

<div xmlns:adobe="http://www.adobe.com/saxon">

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td colspan="2"><h2
id="adobe-recommends">Adobe recommends</h2></td>
<td colspan="2"><h3
id="have-a-tutorial-you-would-like-to-share"><img src="../../img/TinyBlueTutIcon.png"/> <a
href="http://www.adobe.com/community/publishing/download.html"
target="_self">Have a tutorial you would like to share?</a></h3></td>
</tr>
<tr class="even">
<td colspan="4" height="10"></td>
</tr>
<tr class="odd">
<td><span> <img
src="../../img/marco_scabia.png" /> </span></td>
<td width="45%"><h3 id="how-stage3d-works"><a href="http://goo.gl/KB34I"
target="_self">How Stage3D works</a></h3>
<span> <a href="http://goo.gl/sVKdP" target="_self">Marco Scabia:
iFlash3D.com</a> </span></td>
<td><span> <img
src="../../img/marco_scabia.png" /> </span></td>
<td><h3 id="what-is-agal"><a
href="http://goo.gl/kgZ3Y" target="_self">What is AGAL</a></h3>
<span> <a href="http://goo.gl/sVKdP" target="_self">Marco Scabia:
iFlash3D.com</a> </span></td>
</tr>
<tr class="even">
<td colspan="4" height="10"></td>
</tr>
<tr class="odd">
<td><span> <img
src="../../img/marco_scabia.png" /> </span></td>
<td width="45%"><h3 id="vertex-and-fragment-shaders"><a
href="http://goo.gl/EfT4p" target="_self">Vertex and fragment
shaders</a></h3>
<span> <a href="http://goo.gl/sVKdP" target="_self">Marco Scabia:
iFlash3D.com</a> </span></td>
<td><span> <img
src="../../img/bytearrayORG.png" /> </span></td>
<td style="text-align: right;" width="45%"><h3
id="handling-scenarios-with-stage3d"><a href="http://goo.gl/cNLn5"
target="_self">Handling scenarios with Stage3D</a></h3>
<span> Thibault Imbert </span></td>
</tr>
<tr class="even">
<td colspan="4" height="10"></td>
</tr>
<tr class="odd">
<td><span> <img
src="../../img/adobe_logo.png" /> </span></td>
<td width="45%"><h3 id="working-with-the-proscenium-framework"><a
href="http://goo.gl/CA3iC" target="_self">Working with the Proscenium
framework</a></h3>
<span> Adobe </span></td>
<td></td>
<td width="45%"></td>
</tr>
</tbody>
</table>

</div>

- [Basics of 3D display objects](./basics-of-3d-objects.md)
- [Understanding 3D display objects in Flash Player and the AIR runtime](./understanding-3d-display-objects-in-flash-player-and-the-air-runtime.md)
- [Creating and moving 3D display objects](./creating-and-moving-3d-display-objects.md)
- [Projecting 3D objects onto a 2D view](./projecting-3d-objects-onto-a-2d-view.md)
- [Example: Perspective projection](./example-perspective-projection.md)
- [Performing complex 3D transformations](./performing-complex-3d-transformations.md)
- [Using triangles for 3D effects](./using-triangles-for-3d-effects.md)

</div>

<div>

<div>

</div>

</div>
