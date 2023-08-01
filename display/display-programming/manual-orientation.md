# Manual orientation

You can control the stage orientation using the Stage `setOrientation()` or
`setAspectRatio()` methods.

#### Setting the stage orientation

You can set the stage orientation at runtime using the `setOrientation()` method
of the Stage object. Use the string constants defined by the StageOrientation
class to specify the desired orientation:

    this.stage.setOrientation( StageOrientation.ROTATED_RIGHT );

Not every device and operating system supports every possible orientation. For
example, Android 2.2 does not support programmatically choosing the rotated-left
orientation on portrait-standard devices and does not support the upside-down
orientation at all. The `supportedOrientations` property of the stage provides a
list of the orientations that can be passed to the `setOrientation()` method:

    var orientations:Vector.<String> = this.stage.supportedOrientations;
    for each( var orientation:String in orientations )
    {
        trace( orientation );
    }

#### Setting the stage aspect ratio

If you are primarily concerned about the aspect ratio of the stage, you can set
the aspect ratio to portrait or landscape. You can set the aspect ratio in
either the AIR application descriptor or, at run time, using the Stage
`setAspectRatio()` method:

    this.stage.setAspectRatio( StageAspectRatio.LANDSCAPE );

The runtime chooses one of the two possible orientations for the specified
aspect ratio. This may not match the current device orientation. For example,
the default orientation is chosen in preference to the upside-down orientation
(AIR 3.2 and earlier) and the orientation appropriate for the slide-out keyboard
is chosen in preference to the opposite orientation.

**(AIR 3.3 and higher)** Starting with AIR 3.3 (SWF version 16), you can also
use the `StageAspectRatio.ANY` constant. If `Stage.autoOrients` is set to `true`
and you call `setAspectRatio(StageAspectRatio.ANY)`, your application has the
capability to re-orient to all orientations (landscape-left, landscape-right,
portait, and portrait-upside-down). Also new in AIR 3.3, the aspect ratio is
persistent, and further rotation of the device is constrained to the specified
orientation.

#### Example: Setting the stage orientation to match the device orientation

The following example illustrates a function that updates the stage orientation
to match the current device orientation. The stage `deviceOrientation` property
indicates the physical orientation of the device, even when auto-orientation is
turned off.

    function refreshOrientation( theStage:Stage ):void
    {
        switch ( theStage.deviceOrientation )
        {
            case StageOrientation.DEFAULT:
                theStage.setOrientation( StageOrientation.DEFAULT );
                break;
            case StageOrientation.ROTATED_RIGHT:
                theStage.setOrientation( StageOrientation.ROTATED_LEFT );
                break;
            case StageOrientation.ROTATED_LEFT:
                theStage.setOrientation( StageOrientation.ROTATED_RIGHT );
                break;
            case StageOrientation.UPSIDE_DOWN:
                theStage.setOrientation( StageOrientation.UPSIDE_DOWN );
                break;
            default:
                //No change
        }
    }

The orientation change is asynchronous. You can listen for the
`orientationChange` event dispatched by the stage to detect the completion of
the change. If an orientation is not supported on a device, the
`setOrientation()` call fails without throwing an error.
