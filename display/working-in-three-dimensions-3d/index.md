# Working in three dimensions (3D)

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

[Stage3D](https://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/flash/display/Stage3D.html)
provides a very low-level API. In an application, you are encouraged to use a 3D
framework that supports Stage3D. You can create your own framework or use one of
several commercial and open source frameworks already available.

For more information about developing 3D applications using Stage3D and about
available 3D frameworks, visit the
[Flash Player Developer Center: Stage 3D](http://goo.gl/hlzhB).

- [Basics of 3D display objects](./basics-of-3d-objects.md)
- [Understanding 3D display objects in Flash Player and the AIR runtime](./understanding-3d-display-objects-in-flash-player-and-the-air-runtime.md)
- [Creating and moving 3D display objects](./creating-and-moving-3d-display-objects.md)
- [Projecting 3D objects onto a 2D view](./projecting-3d-objects-onto-a-2d-view.md)
- [Example: Perspective projection](./example-perspective-projection.md)
- [Performing complex 3D transformations](./performing-complex-3d-transformations.md)
- [Using triangles for 3D effects](./using-triangles-for-3d-effects.md)

## Adobe recommends

> <h3 id="how-stage3d-works"><a href="http://goo.gl/KB34I" target="_self"><img src="../../img/marco_scabia.png" /> How Stage3D works</a></h3>
> <a href="http://goo.gl/sVKdP" target="_self">Marco Scabia:
> iFlash3D.com</a>

> <h3 id="what-is-agal"><img src="../../img/marco_scabia.png" /> <a href="http://goo.gl/kgZ3Y" target="_self">What is AGAL</a></h3>
> <a href="http://goo.gl/sVKdP" target="_self">Marco Scabia: iFlash3D.com</a>

> <h3 id="vertex-and-fragment-shaders"><a href="http://goo.gl/EfT4p" target="_self"><img src="../../img/marco_scabia.png" /> Vertex and fragment shaders</a></h3>
> <a href="http://goo.gl/sVKdP" target="_self">Marco Scabia: iFlash3D.com</a>

> <h3 id="handling-scenarios-with-stage3d"><a href="http://goo.gl/cNLn5" target="_self"><img src="../../img/bytearrayORG.png" /> Handling scenarios with Stage3D</a></h3>
> Thibault Imbert

> <h3 id="working-with-the-proscenium-framework"><a href="http://goo.gl/CA3iC" target="_self"><img src="../../img/adobe_logo.png" /> Working with the Proscenium framework</a></h3>
> Adobe
